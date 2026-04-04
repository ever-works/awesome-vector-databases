## Overview

QBit is a column type in ClickHouse designed for vector search that stores floats as bit planes instead of whole numbers. It enables users to choose how many bits to read during vector search, tuning recall and performance without changing the underlying data.

## How It Works

- When data is inserted into a QBit column, it is transposed so that all first bits line up together, all second bits line up together, and so on. These groups are called bit planes.
- Each group is stored in a separate FixedString(N) column, and all groups are bundled into a single Tuple that forms the QBit underlying structure.
- During search, ClickHouse reads only the required subcolumns to reconstruct data up to the user-specified precision.
- Untransposition (converting back from grouped bit representation to full vectors) is done efficiently using SIMD instructions (AVX-512 intrinsics).
- Distance calculations leverage the SimSimd library for vectorized computations.

## Supported Types

- BFloat16
- Float32
- Float64

## Key Features

- **Query-time precision tuning**: Adjust precision and speed trade-off dynamically at query time
- **No upfront decisions**: No need to choose quantization level or ANN parameters in advance
- **No data duplication**: Unlike traditional quantization, doesn't require keeping a quantized copy alongside original data
- **No in-memory index**: Works directly with stored data rather than maintaining an in-memory index like HNSW
- **Irreversible precision loss avoided**: Original values remain intact; precision is controlled at read time

## Performance

- Benchmarking on the HackerNews dataset (~29 million Float32 embeddings) achieved nearly 2x speed-up with good recall
- On DBpedia dataset (1 million articles with Float32 embeddings), brute-force search processed 10M rows in 1.157s with 6.05 GiB peak memory, while QBit with precision 5 processed 8.46M rows in 0.271s with 739.82 MiB peak memory
- Computational complexity remains O(n) - if the dataset fits comfortably in RAM with an HNSW index, HNSW is still the fastest choice

## Usage Example

```sql
CREATE TABLE fruit_animal
(
    word String,
    vec QBit(Float64, 5)
)
ENGINE = MergeTree
ORDER BY word;

SELECT word, L2DistanceTransposed(vec, [...], 16) AS distance
FROM fruit_animal
ORDER BY distance;
```

Precision level 16 on Float64 (64 bits) reads only 25% of the data, skipping 75%.

## Comparison with Other Methods

| Approach | Precision | Speed | Trade-offs |
|----------|-----------|-------|------------|
| Brute-force | Perfect | Slow | High resource usage |
| HNSW | Great | Fast | Index must fit in memory, parameters chosen upfront |
| QBit | Flexible | Flexible | Still O(n) for number of records |

## Pricing

QBit is part of ClickHouse, which is open-source and free to use.