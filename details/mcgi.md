## Overview

MCGI (Manifold-Consistent Graph Indexing) is a geometry-aware and disk-resident indexing method that leverages Local Intrinsic Dimensionality (LID) to dynamically adapt search strategies to the data's intrinsic geometry. Published in January 2026.

## Core Problem

Graph-based Approximate Nearest Neighbor (ANN) search often suffers from performance degradation in high-dimensional spaces due to the "Euclidean-Geodesic mismatch," where greedy routing diverges from the underlying data manifold.

## Key Innovation

Unlike standard algorithms that treat dimensions uniformly, MCGI modulates its beam search budget based on in situ geometric analysis, eliminating dependency on static hyperparameters.

## Performance Results

### High-dimensional datasets (GIST1M, 960 dimensions)
- Achieves 5.8× higher throughput at 95% recall compared to state-of-the-art DiskANN
- Reaches 375 QPS through manifold-aware routing that minimizes strictly necessary disk reads

### Billion-scale datasets (SIFT1B)
- Reduces high-recall query latency by 3× on billion-scale datasets
- Maintains performance parity on standard lower-dimensional datasets

## Theoretical Foundation

Theoretical analysis confirms that MCGI enables improved approximation guarantees by preserving manifold-consistent topological connectivity.

## Research Impact

MCGI addresses the critical challenge of maintaining search quality in high-dimensional spaces while operating efficiently from disk storage, making it suitable for billion-scale vector search applications.