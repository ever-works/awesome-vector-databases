## Overview

YugabyteDB's Vector LSM is a decoupled, pluggable indexing layer that separates vector search logic from the rest of the database engine, enabling easy integration with multiple ANN (Approximate Nearest Neighbor) backends.

## Architecture

Vector LSM works like an LSM tree built for vector indexes: vectors are first inserted into an in-memory buffer and indexed using HNSW-based libraries like USearch, then flushed to disk as immutable vector chunks once full, with searches fanning out across all in-memory and on-disk vector indexes, and results filtered using MVCC rules to ensure consistency.

## Key Benefits

- **Pluggability**: Easy to swap ANN backends
- **Consistency**: MVCC integration ensures transactional guarantees
- **Scalability**: Co-partitioned layout enables horizontal scaling
- **Performance**: Sub-second query latency at billion-vector scale

## Co-partitioned Vector Index

YugabyteDB uses a co-partitioned vector index layout, where vector indexes are stored in the same tablets as the corresponding table rows, ensuring tight data locality and operational advantages.

## Benchmark Performance

In benchmarking with the Deep1B dataset, YugabyteDB successfully indexed 1 billion 96-dimensional vectors, achieving a recall of 96.56% and sub-second query latency.

## Pricing

Included in YugabyteDB, open-source and commercial versions available.