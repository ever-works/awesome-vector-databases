## Overview

ruvector-core provides the foundational vector database engine with HNSW indexing optimized for speed and accuracy.

## Features

- HNSW indexing with configurable ef_search for 100% recall
- SIMD-optimized distance calculations (Euclidean, Cosine, Dot Product)
- Adaptive compression tiers (f32 to binary, 1x-32x)
- Multi-threaded search and batch inserts
- Persistence via snapshots

## Performance

| Config | QPS | p50 Latency |
|--------|-----|-------------|
| Single-threaded | 394 | 1.80ms |
| Multi-threaded (16) | 3,597 | 2.86ms |
| SIMD Optimized | 1,216 | 0.78ms |

## Pricing

Free and open-source.