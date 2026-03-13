## Overview

The TreeAH index is based on Google's ScaNN (Scalable Nearest Neighbors) algorithm, which is used in a multitude of Google services for similarity search. The TreeAH index type is named for its combination of a tree-like structure and its use of Asymmetric Hashing (AH), a core quantization technique from the underlying ScaNN algorithm.

## Asymmetric Hashing (AH)

The main difference with the IVF index is the use of asymmetric hashing (the "AH" in TreeAH), which uses product quantization to compress embeddings. The "asymmetric" aspect refers to the fact that:
- The query vector is kept in its full-precision form
- The database vectors are compared in their compressed, quantized form

## How TreeAH Works

### Compression

The vectors are compressed with product quantization, a technique that reduces their memory usage. The compressed vectors are then stored in the index tables instead of the original vectors, thus reducing vector index sizes.

### Search Process

When the VECTOR_SEARCH or AI.SEARCH function runs:
1. A candidate list for each query vector is efficiently computed using asymmetric hashing
2. Hardware-optimized approximate distance calculations are performed
3. Candidates are re-scored and re-ranked using exact embeddings

## Performance Benefits

Coupled with a CPU-optimized distance computation algorithm, vector search using TreeAH can be:
- Orders of magnitude faster than IVF
- More cost-efficient
- 10x faster index generation
- Smaller memory footprint (only compressed embeddings stored)

## Optimization

The TreeAH algorithm is optimized for batch queries that process hundreds or more query vectors.

## Pricing

Available as part of Google Cloud BigQuery and Vertex AI services.