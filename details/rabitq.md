# RaBitQ

**Category:** SDKs & Libraries  
**Slug:** rabitq  
**Source:** https://github.com/gaoj0017/RaBitQ

## Description
RaBitQ is an open-source implementation of the SIGMOD 2024 method "Quantizing High-Dimensional Vectors with a Theoretical Error Bound for Approximate Nearest Neighbor Search." It provides vector quantization and compression techniques aimed at improving the efficiency and accuracy of approximate nearest neighbor (ANN) search engines and vector databases operating in high-dimensional spaces.

## Features
- Implementation of the RaBitQ quantization method for high-dimensional vectors.
- Designed for approximate nearest neighbor search in Euclidean space.
- Vector quantization and compression suitable for high-dimensional ANN search engines and vector databases.
- Theoretical error bound for distance estimation between vectors.
- Reference implementation aligned with the SIGMOD 2024 publication.
- Example datasets and preprocessing scripts under `./data/` with detailed instructions in `./data/README.md`.
- Index construction components (e.g., IVF-RaBitQ) under `./src/ivf_rabitq.h`.
- Supporting utilities for vector space handling and fast scan operations (`space.h`, `fast_scan.h`).
- Result generation pipeline with outputs stored under `./results/`.
- Dependency on Eigen for linear algebra operations.
- Technical report (`technical_report.pdf`) and published paper citation information for research use.
- Companion, more practical library referenced at **RaBitQ-Library** for extended/production-focused usage.

## Technical Requirements
- C++ toolchain capable of building the code in `./src/`.
- Eigen library installed and available to the build system.

## Typical Workflow
1. Download and preprocess datasets using the scripts and instructions in `./data/README.md`.
2. Build and run the index construction (e.g., IVF-RaBitQ) from the `src` directory.
3. Run query tests over the indexed datasets.
4. Inspect generated metrics and outputs in the `./results/` directory.

## License
- The repository includes a `LICENSE` file (see GitHub project for exact terms).

## Pricing
- Open-source software; no pricing information is provided (use is governed by the repository’s license).