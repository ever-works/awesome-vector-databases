## Overview

JVector is a graph-based ANN index merging the HNSW and DiskANN designs, with composable extensions for vector search.

## Architecture

- Multi-layer graph with non-blocking concurrency control, scaling linearly with cores.
- Upper layers: in-memory adjacency lists for quick navigation without IO.
- Bottom layer: on-disk adjacency lists.
- Two-pass searches:
  - First pass: lossily compressed vectors (Product Quantization with optional anisotropic weighting, Binary Quantization, Fused PQ).
  - Second pass: full float32 vectors or NVQ (non-uniform quantization).
- Index construction uses two-pass searches for larger-than-memory datasets.

## Features

- Supports incremental construction and updates.
- Multi-release JAR for Java 11+ compatibility, with optimizations for Java 20+ Vector API.
- Includes benchmarks (Bench, SiftSmall) and tutorials.

## Pricing

Free and open-source.