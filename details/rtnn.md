# RTNN

## Overview
RTNN is a research prototype system and codebase that accelerates neighbor search by mapping it onto Nvidia GPU hardware ray tracing units (RT cores). It focuses on low-dimensional spaces (≤3D), as commonly found in engineering and scientific simulations (e.g., particles, surface samples in CFD, graphics, and vision). The implementation is primarily based on the OptiX ray tracing API with CUDA used for parallel helper routines.

- **Category:** SDKs & Libraries  
- **Use cases:** Vector / spatial similarity search, neighbor search in 2D/3D simulations and analysis  
- **Source:** https://github.com/horizon-research/rtnn

## Features

### Neighbor Search Capabilities
- Supports **fixed-radius search (range search)**.  
- Supports **K-nearest neighbor (KNN) search**.  
- Interface assumes:
  - A **search radius** `r` for both range and KNN searches.
  - A **maximum neighbor count** `K` for both KNN and range searches.
- Can **emulate unbounded KNN** by using a very large `r`.
- Can **emulate unbounded range search** by using a very large `K`.
- Designed for **low-dimensional (2D/3D) spatial neighbor search**, common in physical simulations and geometric data.

### Performance & Acceleration
- Uses **Nvidia RT cores** (hardware ray tracing units) to accelerate neighbor search.  
- Demonstrates **order-of-magnitude speedups** over traditional GPU (CUDA-only) neighbor search implementations, as reported in an associated PPoPP 2022 paper.
- Explores **ray tracing hardware** as an alternative acceleration path to standard CPU/CUDA approximate nearest neighbor (ANN) indexes for similarity search workloads.

### Implementation & Technology
- Built primarily on **Nvidia OptiX** (ray tracing programming interface).
- Uses **CUDA** to parallelize many **non-ray-tracing helper functions**.
- Includes required **OptiX SDK 7.1.0 headers** directly in the repository (no separate SDK install required for those headers).
- Repository structure:
  - `include/` – OptiX headers (copied from OptiX SDK 7.1.0, unmodified).
  - `src/` – Source code for RTNN implementation.

### Design Considerations
- **Search radius `r`** even in KNN:
  - Reflects practical need to discard far-away neighbors whose influence (e.g., physical forces) is negligible.
- **Bound on `K`** even in range search:
  - Controls memory usage.
  - Conforms to downstream tasks that expect a fixed or bounded number of neighbors.

### Research Context
- Technical design and evaluation are discussed in a **PPoPP 2022 paper**: https://horizon-lab.org/pubs/ppopp22.pdf.
- Performance has been **significantly improved since** the version described in the paper.

## Requirements
- Nvidia GPU with **RT cores** (supports hardware ray tracing).
- **OptiX 7.1.0** headers are included; external installation of the SDK is not strictly required for those headers.
- CUDA environment for building and running helper kernels.

## Pricing
- **Open-source library** (license included in `LICENSE` file in the repository).  
- No pricing information is provided; usage is governed by the repository’s open-source license.