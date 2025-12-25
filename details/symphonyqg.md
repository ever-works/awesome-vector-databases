# SymphonyQG

**Category:** SDKs & Libraries  
**Brand:** gouyt13  
**Source:** https://github.com/gouyt13/SymphonyQG

SymphonyQG is a research codebase and ANN indexing method that integrates vector quantization with graph-based indexing to build efficient approximate nearest neighbor (ANN) indexes for high-dimensional vector search. It is aimed at vector databases and similarity search workloads where combining compact quantized codes with navigable graphs improves recall–latency trade-offs and reduces memory usage.

---

## Features

### Core Capabilities
- **Approximate Nearest Neighbor (ANN) search** for high-dimensional vectors.
- **Hybrid quantization + graph approach** ("quantized graph") to balance recall, latency, and memory footprint.
- **Configurable similarity metric** (e.g., choose distance metric when creating the index).
- **Bounded graph degree** via `degree_bound` parameter to control graph connectivity and index size.

### Library Structure
- `data/`
  - Contains datasets and pre-built indices used for experiments and reproduction.
- `symqglib/`
  - **`index/`**
    - `fastscan/`: helper functions for FastScan-style operations.
    - `qg/`: implementation of the quantized graph index.
  - `third/`: third-party dependencies needed by the library.
  - `utils/`: common utility functions.
- `python/`
  - Python bindings exposing the core C++ ANN index to Python.
- `reproduce/`
  - Scripts and code to reproduce experimental results, including configuration and dataset handling.
- `test/`
  - Tests for validating core functionality (implied by directory name).

### Python API (Recommended Interface)

#### Index Construction
```python
symphonyqg.Index(index_type, metric, num_elements, dimension, degree_bound=32)
```
- **Parameters**
  - `index_type`: type of ANN index to build (e.g., specific quantization/graph variant; exact values in repo docs/code).
  - `metric`: distance/similarity metric (e.g., L2, inner product; details in repo).
  - `num_elements`: number of vectors the index will hold.
  - `dimension`: dimensionality of each vector.
  - `degree_bound` (optional, default = 32): upper bound on graph node degree to control index sparsity and memory.

#### Methods
- **`build_index(data, EF, num_iter=3, num_threads=ALL_THREADS)`**
  - Builds the ANN index from training data.
  - `data`: input dataset, shape `(num_elements, dimension)`, `dtype=float32`.
  - `EF`: construction/search breadth parameter (controls exploration during graph-based search/build).
  - `num_iter`: number of construction iterations (default `3`).
  - `num_threads`: number of threads to use (default `ALL_THREADS`).

- **`save(filename)`**
  - Saves the built index to disk.

- **`load(filename)`**
  - Loads a previously saved index from disk.

- **`set_ef(EF)`**
  - Adjusts the runtime search parameter `EF` to trade off latency vs. recall without rebuilding the index.

- **`search(query, k)`**
  - Performs ANN search.
  - `query`: query vector(s), shape `(dimension,)` or `(1, dimension)`, `dtype=float32`.
  - `k`: number of nearest neighbors to retrieve.

### Examples & Reproducibility
- **Python examples**: basic usage via Python bindings (creation, build, search, save/load) indicated in `README.md`.
- **Real-world datasets**: example configurations and scripts under `./reproduce`.
- **Datasets description**: additional details in `./data/README.md`.
- **Reproduction guide**: steps for experiments in `./reproduce/README.md`.

### C++ Usage
- C++ examples are provided (mentioned under “C++ examples”) for users who want to integrate SymphonyQG directly at the C++ level instead of Python.

### License
- A `LICENSE` file is present in the repository; consult it directly for the exact open-source license terms.

---

## Pricing

SymphonyQG is an open-source research codebase hosted on GitHub. No pricing or paid plans are specified in the available content.