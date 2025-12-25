# vsag

**Brand:** Alibaba  
**Category:** SDKs & Libraries  
**Type:** Open‑source vector indexing library

## Overview
vsag is an open-source C++ vector indexing library for high-dimensional similarity search, designed to handle vector datasets that may not fit entirely in memory. It implements efficient vector search algorithms, including approximate nearest neighbor (ANN) search, and provides a Python wrapper package, **pyvsag**, for easier integration in Python environments.

## Features

- **Vector similarity search**
  - Supports high-dimensional similarity search and approximate nearest neighbor (ANN) queries.
  - Designed to work with vector sets of various sizes, including those that do not fit into memory.

- **Indexing algorithms**
  - Implements the VSAG algorithm for efficient vector indexing and search.
  - Includes **SINDI** algorithm optimized for sparse vector search.
  - Provides example implementations such as HNSW-based indexing (e.g., `101_index_hnsw.cpp`, `example_hnsw.py`).

- **Performance characteristics**
  - SINDI algorithm for sparse vector search targets state-of-the-art performance, significantly improving QPS (queries per second) compared with prior solutions in internal tests.
  - Demonstrated efficiency on:
    - **Sparse-full-inner-product** tasks, with substantial QPS gains over previous SOTA and baseline algorithms on benchmark datasets.
    - **gist-960-euclidean** benchmarks, tested in the ann-benchmarks framework.
  - Benchmarks reported on multi-core CPU environments (e.g., Intel Xeon CPUs, AWS r6i.16xlarge), suitable for large-scale, CPU-based deployments.

- **Automatic parameter generation**
  - Provides methods to generate algorithm parameters based on vector dimensions and data scale.
  - Aims to let developers use the library effectively without needing deep knowledge of the underlying algorithms.

- **Language support**
  - **C++** core implementation.
  - **Python** wrapper package: **pyvsag** available on PyPI.

- **Integration & build**
  - CMake integration via `FetchContent` for easy inclusion in C++ projects.
  - Public C++ headers available via `include` directory.
  - Example CMake configuration for fetching and linking `vsag` in user projects.
  - Build-from-source instructions provided in a `DEVELOPMENT.md` guide in the repository.

- **Examples and usage**
  - C++ and Python example programs provided in the `examples` directory.
  - Starter examples include:
    - `101_index_hnsw.cpp` (C++)
    - `example_hnsw.py` (Python)

- **Ecosystem adoption**
  - Used by multiple database and data systems, including (as listed in the repo):
    - OceanBase
    - TuGraph
    - GreptimeDB
    - Hologres
    - PolarDB

## Tech Stack
- Core language: **C++** (C++11 standard or later)
- Build system: **CMake** (3.11+ recommended)
- Python wrapper: **pyvsag** (via PyPI)

## Pricing
vsag is an open-source library. No pricing plans are listed; usage is free under the terms of its open-source license (see the GitHub repository for license details).

## Links
- Source code & documentation: https://github.com/alipay/vsag  
- Python package (pyvsag): https://pypi.org/project/pyvsag/  
- Benchmarks information: https://ann-benchmarks.com/ (external benchmark framework referenced by the project)