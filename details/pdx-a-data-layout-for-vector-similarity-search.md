# PDX: A Data Layout for Vector Similarity Search

- **Type:** Research paper / data layout technique
- **Category:** Curated resource lists
- **Source:** [arXiv – PDX: A Data Layout for Vector Similarity Search](https://arxiv.org/pdf/2503.04422)
- **Authors:** Leonardo Kuffo, Elena Krippner, Peter Boncz
- **Venue:** SIGMOD 2025

## Overview
PDX (Partition Dimensions Across) is a proposed data layout for storing high-dimensional vectors (e.g., embeddings) aimed at accelerating both exact and approximate vector similarity search (K-Nearest Neighbour Search / Vector Similarity Search). It reorganizes vectors within blocks into a vertical, dimension-oriented layout to improve memory locality and enable efficient dimension-by-dimension distance computation.

## Features

- **Vertical, dimension-oriented layout**
  - Stores multiple vectors per block.
  - Organizes data “dimensions vertically” rather than as standard horizontal (row-major) vectors.
  - Inspired by the PAX layout, but tailored to high-dimensional vector similarity search.

- **Dimension-by-dimension distance computation**
  - Computes distances one dimension at a time across many vectors in tight loops.
  - Facilitates better cache and memory locality when only a subset of dimensions needs to be inspected.

- **Auto-vectorization-friendly design**
  - Uses scalar code that is amenable to compiler auto-vectorization.
  - Achieves performance gains without custom hand-written SIMD kernels.

- **Performance improvements over horizontal layouts**
  - Reported to outperform SIMD-optimized distance kernels on standard horizontal vector storage by an average of ~40%.
  - Especially efficient when only a limited number of dimensions are fully scanned.

- **Integration with dimension-pruning algorithms**
  - Designed to work with dimension-pruning methods such as:
    - **ADSampling**
    - **BSA**
  - On horizontal layouts, these pruning methods can underperform compared to SIMD-optimized linear scans; on PDX, their performance benefit is restored (reported 2–7× speedups).

- **PDX-BOND pruning strategy**
  - Introduces **PDX-BOND**, a flexible dimension-pruning strategy that:
    - Provides strong performance on exact search.
    - Offers reasonable performance on approximate search.
    - Operates on vector data “as-is,” without requiring preprocessing.
  - Suited for environments with frequent updates, such as dynamic vector databases.

- **Applicability to exact and approximate VSS**
  - Targets both exact K-Nearest Neighbour Search and Approximate Nearest Neighbor Search.
  - Compatible with common distance/similarity metrics (e.g., Euclidean, Cosine, Manhattan).

- **Relevance to vector databases and ANN indexes**
  - Affects internal storage design for vector databases and approximate nearest neighbor (ANN) index structures.
  - Complements existing indexing methods (bucketing, trees, graphs, quantization) by improving low-level data layout and distance computation.

## Use Cases

- Internal storage layer for vector databases and ANN libraries.
- High-throughput similarity search workloads in:
  - Information and multimedia retrieval systems.
  - Data and analytics pipelines.
  - Code completion / co-pilot systems.
  - LLM retrieval-augmented generation and embedding-based search.

## Pricing

- Not applicable. This is an academic research paper / technique, not a commercial product with pricing plans.