## Overview

VLDB 2024 paper providing systematic survey of vector DB management systems (VDBMS).

## Features

- Architecture classification (storage engines, query processors)
- ANN indexing review: graph (HNSW), tree, hash, quantization
- Query processing & optimization techniques
- Distributed systems and concurrency handling

## Theory/Practice Gaps

- Theoretical ANN recall vs practical trade-offs under filtering/updates
- Memory-centric theory vs disk/persistent indexes in practice
- Single-node prototypes vs production-scale distribution

## Use Cases

- Academic paper selection for literature reviews
- Identifying research gaps in VDBMS
- Guidance for building new vector databases

## Comparisons

| Aspect | VLDB Survey (this paper) | NeurIPS BigANN |
|--------|--------------------------|----------------|
| Focus | Full VDBMS systems | Pure ANN algorithms |
| Scale | System-level | Billion-scale datasets |
| Metrics | Architecture completeness | QPS/recall |

## Publication

**Venue**: VLDB 2024 (Pan et al.)