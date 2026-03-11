## Overview

Approximate Nearest Neighbors (ANN) algorithms find near-neighbors quickly by sacrificing perfect accuracy for speed, essential for large-scale vector search.

## Why ANN?

### Exact Search Problems
- Linear scan: O(N) complexity
- Infeasible for billions of vectors
- Prohibitive latency

### ANN Solution
- Sub-linear search: O(log N) or better
- 90-99% recall typical
- Millisecond latencies

## Algorithm Categories

### Graph-Based
- HNSW, NSW, Vamana
- Best recall-speed tradeoff

### Clustering
- IVF, SPANN
- Partitions space

### Hashing
- LSH
- Very high dimensions

### Trees
- Annoy, KD-Tree
- Lower dimensions

## Key Metrics

- **Recall**: % of true neighbors found
- **Latency**: Query time
- **Throughput**: Queries per second
- **Memory**: Storage requirements

## Tradeoffs

- Accuracy vs Speed
- Memory vs Performance
- Build time vs Query time
- Update efficiency

## Benchmarks

- ANN-Benchmarks
- Big-ANN Challenge
- MTEB (for embeddings)

## Pricing

Algorithms, no licensing.