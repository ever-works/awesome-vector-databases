## Overview

Understanding the computational complexity of ANN algorithms helps choose the right method for your scale and performance requirements.

## Time Complexity

### HNSW
- **Build**: O(N log N × M)
- **Query**: O(log N) on average
- **Space**: O(N × M) where M is max connections

### IVF
- **Build**: O(N × k × d × iterations) for clustering
- **Query**: O(nprobe × N/nlist × d)
- **Space**: O(N × d)

### LSH
- **Build**: O(N × L × k) where L is tables, k is functions
- **Query**: O(NL/b) where b is buckets
- **Space**: O(N × L)

### Product Quantization
- **Build**: O(N × m × k × d/m) where m is subspaces
- **Query**: O(N) with faster distance computation
- **Space**: O(N × m × log k)

## Space-Time Trade-offs

**HNSW**: High memory, fast queries
**IVF-PQ**: Low memory, moderate speed
**LSH**: Moderate memory, sublinear queries

## Scalability

- **Million-scale**: Most algorithms work well
- **Billion-scale**: HNSW, IVF-PQ, DiskANN
- **Trillion-scale**: Specialized distributed systems

## Choosing by Scale

**< 1M vectors**: HNSW (best quality)
**1M - 100M**: IVF-PQ or HNSW with quantization
**100M - 1B**: IVF-PQ, DiskANN
**> 1B**: Distributed IVF-PQ, specialized systems

## Pricing

Not applicable (algorithmic analysis).