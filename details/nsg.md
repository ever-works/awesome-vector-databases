---
title: NSG
slug: nsg
url: https://github.com/ZJULearning/nsg
brand: zjulearning
category: sdks-libraries
featured: false
images:
  - https://opengraph.githubassets.com/1/ZJULearning/nsg
Tags:
  - ann
  - graph-index
  - similarity-search
---

## Overview

NSG (Navigating Spread-out Graph) is a graph-based approximate nearest neighbor search (ANNS) algorithm designed for large-scale, high-dimensional vector similarity search. It builds a sparse navigable graph over dense real-valued vectors to enable efficient, metric-free approximate nearest neighbor queries, and is provided as a reference implementation that can be integrated into custom vector retrieval systems.

## Features

- **Graph-based ANN index**  
  Builds a sparse navigable graph structure over vector datasets for approximate nearest neighbor search.

- **Approximate Nearest Neighbor Search (ANNS)**  
  Implements ANNS for dense real-valued vectors, targeting high efficiency and scalability.

- **Metric-free design**  
  Designed for metric-free, large-scale ANN search on dense vectors, not tied to a specific distance metric.

- **Reference implementation of NSG algorithm**  
  Implements the algorithm from the PVLDB paper *“Fast Approximate Nearest Neighbor Search With The Navigating Spread-out Graphs”*.

- **Large-scale / billion-scale readiness**  
  Used in production (e.g., Taobao search engine) for billion-scale ANN search in e-commerce scenarios, indicating suitability for very large datasets.

- **Library / SDK structure**  
  - C++ source code under `src` and `include/efanna2e`
  - Python bindings under `pynsg`
  - CMake-based build configuration (`CMakeLists.txt`)
  - Dockerfile for containerized builds and experiments
  - Test suite under `tests` for validation

- **Research-oriented codebase**  
  Organized to support experimentation and benchmarking of NSG against other ANN algorithms, including figures and performance evaluation materials.

## Technology

- Language: Primarily C++ (with Python bindings via `pynsg`).  
- Build system: CMake; Docker support via provided `Dockerfile`.

## Licensing

- License file included (`LICENSE`) in the repository; users should consult it directly for exact terms.

## Pricing

- NSG is an open-source research implementation hosted on GitHub. No pricing or paid plans are specified in the available content.