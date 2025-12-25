# EFANNA

**Category:** SDKs & Libraries  
**Tags:** ann, high-performance, vector-indexing  
**Source:** https://github.com/ZJULearning/efanna

## Overview
EFANNA is a C++ library for extremely fast approximate nearest neighbor (ANN) search on large-scale data. It implements the EFANNA algorithm described in the paper *“EFANNA: Extremely Fast Approximate Nearest Neighbor Search Algorithm Based on kNN Graph”* and provides both ANN search and approximate kNN graph construction.

## Features
- **Approximate nearest neighbor search**
  - High-performance ANN search on large-scale vector datasets.
  - Designed as a building block for custom vector search and retrieval infrastructure.

- **kNN graph construction**
  - Efficient construction of approximate k-nearest neighbor graphs.
  - Can be used as a base structure for various graph-based search algorithms.

- **Flexible initialization structures**
  - Supports multiple hierarchical structures for search initialization, including:
    - Randomized KD-trees.
    - Random projection trees.
    - Hierarchical clustering trees.
    - Multi-table hashing (via the provided hashing samples).

- **Algorithm framework**
  - Implements the EFANNA framework as described in the associated research paper.
  - Separated modules under `algorithm`, `general`, and `samples` directories for experimentation and extension.

- **Language and ecosystem**
  - C++ implementation (`efanna.hpp`, Makefiles provided).
  - Example code and usage patterns under `samples/`.
  - Additional MATLAB-related utilities in the `matlab/` directory.

- **Documentation and examples**
  - `docs/` folder for algorithm and usage documentation (as provided in the repository).
  - Sample programs demonstrating index construction and query workflows.

- **Performance focus**
  - Designed specifically for speed on ANN search and kNN graph construction tasks.
  - Benchmark references and figures for ANN search performance on standard datasets (e.g., SIFT) included in the repository.

## Pricing
EFANNA is an open-source library hosted on GitHub. No pricing or paid plans are specified in the provided content.

## License
- A `LICENSE` file is present in the repository.  
- Consult the repository’s `LICENSE` file for the exact license terms and conditions.