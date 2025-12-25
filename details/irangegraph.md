# iRangeGraph

**Category:** SDKs & Libraries  
**Tags:** ann, graph-index, similarity-search  
**Source:** https://github.com/YuexuanXu7/iRangeGraph

## Overview

iRangeGraph is a graph-based Approximate Nearest Neighbor (ANN) indexing method and reference implementation tailored for **range-filtering nearest neighbor search**. It builds a specialized graph index over vector data that are ordered by an attribute, enabling efficient similarity search under attribute range constraints.

Implementation corresponds to the paper: *“iRangeGraph: Improvising Range-dedicated Graphs for Range-filtering Nearest Neighbor Search”* (arXiv:2409.02571).

## Features

- **Range-filtering ANN search**
  - Supports nearest neighbor search with explicit range constraints on an attribute.
  - Designed for single-attribute range-filtered queries over sorted data.

- **Graph-based index structure**
  - Constructs a range-dedicated graph index over the dataset.
  - Configurable graph degree via `--M` (controls connectivity / out-degree of nodes).
  - Uses `--ef_construction` to control the size of the candidate/result set during index building.

- **Binary data format support**
  - Expects data in `.bin` format:
    - First 4 bytes: number of points (int).
    - Next 4 bytes: dimensionality (int).
    - Following `n * d * sizeof(float)` bytes: contiguous float vectors (one data point at a time).
  - Data must be **sorted in ascending order by the range attribute**.

- **Index construction CLI**
  - Build-time parameters:
    - `--data_path` – path to input dataset in the specified `.bin` layout.
    - `--index_file` – output path for the constructed graph index in `.bin` format.
    - `--M` – graph degree.
    - `--ef_construction` – search breadth during index construction.
    - `--threads` – number of threads for parallel index building.

- **Single-attribute search CLI**
  - Query-time parameters:
    - `--data_path` – path to the underlying data (same `.bin` format used to build the index, sorted by attribute).
    - `--query_path` – queries in `.bin` format using the same header + vector layout.
    - `--range_saveprefix` – directory prefix where query range files will be saved; uses numeric codes (0–9) to denote different query range fractions.
  - Supports batch query execution from file.

- **CMake-based build**
  - Uses `CMakeLists.txt` for configuration and build.
  - C++ implementation with `include/` and `tests/` directories for headers and test code.

- **Research reference implementation**
  - Repository includes a `technical_report.pdf` with additional algorithmic and experimental details.
  - Licensed via the included `LICENSE` file (open-source; see repository for exact terms).

## Typical Workflow

1. **Prepare data** in the required `.bin` layout and sort it ascending by the attribute used for range filtering.
2. **Build the index** using the index construction command with `--data_path`, `--index_file`, `--M`, `--ef_construction`, and `--threads`.
3. **Run range-filtered ANN queries** by supplying `--data_path`, `--query_path`, and `--range_saveprefix` for single-attribute search.

## Pricing

This is an open-source library hosted on GitHub. No pricing information or paid plans are specified in the available content.