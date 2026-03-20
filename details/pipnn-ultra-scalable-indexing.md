## Overview

PiPNN (Pick-in-Partitions Nearest Neighbors) is a research breakthrough in graph-based ANN index construction published in February 2026. The algorithm fundamentally addresses the "search bottleneck" that existing graph-based methods suffer from during index construction.

## Core Innovation: HashPrune

HashPrune is a novel online pruning algorithm that dynamically maintains sparse collections of edges during graph construction. This innovation enables:
- Bounded memory usage during index construction
- Building higher quality indices without extra intermediate memory
- Efficient bulk distance comparisons via dense matrix multiplication kernels

## How PiPNN Works

The algorithm employs a three-step process:

1. **Partition**: Divides the dataset into overlapping sub-problems
2. **Pick**: Efficiently performs bulk distance comparisons via dense matrix multiplication kernels
3. **Prune**: Streams a subset of the edges into HashPrune for dynamic edge maintenance

## Performance Benchmarks

**Speed Improvements**:
- Up to 11.6× faster than Vamana (DiskANN)
- Up to 12.9× faster than HNSW
- At least 19.1× faster than MIRAGE
- 17.3× faster than FastKCNA

**Quality**: Produces indexes that achieve higher query throughput than competing methods

**Scalability**: Enables building high-quality ANN indexes on billion-scale datasets in under 20 minutes using a single multicore machine

## Memory Efficiency

Unlike traditional approaches that require significant intermediate memory, HashPrune guarantees bounded memory during index construction. This makes PiPNN practical for building very large indexes on machines with limited RAM.

## Use Cases

- Billion-scale vector index construction
- High-quality graph-based ANN indexes
- Memory-constrained index building
- Production deployments requiring fast index updates

## Significance

PiPNN represents a significant advancement in making graph-based ANN indexing practical at billion-scale. The combination of speed, quality, and memory efficiency makes it particularly valuable for production systems.

## Availability

Published as arXiv preprint arXiv:2602.21247 (2026) by Rubel, Tobias, et al.