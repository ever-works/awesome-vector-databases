## Overview

Published in July 2025 (arXiv:2507.10070), this paper presents a GPU-driven asynchronous I/O framework that breaks through the storage-compute bottleneck limiting billion-scale vector search systems.

## The Bottleneck Problem

For billion-scale datasets exceeding GPU memory:
- Data must be loaded from storage (SSD) during search
- I/O bandwidth becomes the limiting factor
- GPU compute sits idle waiting for data
- Traditional synchronous I/O wastes resources

## Asynchronous I/O Framework

The key innovation is overlapping I/O and computation:

1. **Prefetch Next Data**: While GPU processes current batch, asynchronously load next batch
2. **Pipeline Execution**: Continuous stream of data to GPU
3. **Minimize Idle Time**: Keep GPU utilized while I/O happens in background
4. **Adaptive Scheduling**: Adjust prefetch based on query patterns

## GPU-Driven Design

Unlike CPU-managed I/O:
- GPU directly controls data movement
- Reduces CPU bottleneck
- Lower latency for I/O decisions
- Better alignment with GPU compute patterns

## Performance Benefits

- **Throughput**: Maximizes GPU utilization by eliminating I/O wait time
- **Latency**: Reduces query latency through intelligent prefetching
- **Scalability**: Enables billion-scale search with single GPU
- **Efficiency**: Better resource utilization vs. synchronous approaches

## Technical Contributions

### Smart Prefetching
Algorithms to predict which data will be needed next based on graph traversal patterns

### Overlap Optimization
Methods to maximize overlap between I/O and computation phases

### Memory Management
Strategies for efficiently managing limited GPU memory as a cache for SSD data

## Use Cases

- Billion-scale semantic search on single GPU
- Cost-effective large-scale deployments
- Systems where dataset >> GPU memory
- Applications requiring both scale and speed

## Significance

As vector datasets grow, the storage-compute interface becomes critical. This research provides practical techniques for efficiently bridging SSD storage and GPU computation—essential for making billion-scale search economical.

## Availability

ArXiv preprint arXiv:2507.10070 (2025) with detailed algorithms and experimental results.