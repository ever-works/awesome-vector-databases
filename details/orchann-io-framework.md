## Overview

OrchANN (I/O Orchestration Framework for Approximate Nearest Neighbor Search) is a research paper published in 2025 that presents a unified framework for handling skewed out-of-core vector search. The paper addresses the critical challenge of performing billion-scale ANN search when datasets exceed available memory.

## Key Problem

When vector datasets are too large to fit in memory, they must be stored on disk (SSD). This creates significant I/O bottlenecks during search operations, especially for graph-based indexes like HNSW and DiskANN. The challenge becomes even more severe when query workloads are skewed—some regions of the graph are accessed much more frequently than others.

## Solution Approach

OrchANN provides a unified I/O orchestration framework that:
- Intelligently manages data movement between disk and memory
- Optimizes for skewed access patterns in graph-based indexes
- Reduces I/O overhead through strategic prefetching and caching
- Balances latency and throughput for out-of-core vector search

## Technical Innovations

The framework addresses:
- **Skewed Access Patterns**: Real-world queries don't uniformly access all parts of the index
- **Graph Traversal Optimization**: Predicts and prefetches likely-to-be-accessed nodes during search
- **Memory Management**: Efficiently manages limited memory budget for maximum search performance

## Performance Benefits

By orchestrating I/O operations specifically for vector search workloads, OrchANN enables:
- Reduced query latency for billion-scale datasets
- Better handling of skewed query distributions
- Improved resource utilization for disk-based indexes

## Availability

Published as arXiv preprint arXiv:2512.22838 (2025) by Huan, Chengying, et al.