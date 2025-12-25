# ParlayANN

**Category:** SDKs & Libraries  
**Website:** https://github.com/cmuparlay/ParlayANN  
**License:** See `LICENSE` file in repository

## Description
ParlayANN is a C++ library of scalable, deterministic, parallel graph-based approximate nearest neighbor (ANN) search algorithms for high-dimensional vector similarity search. It is designed for use as a core search component in large-scale vector databases and retrieval systems, and builds on parallel primitives from ParlayLib.

## Features
- **Multiple ANN algorithms implemented**  
  - DiskANN  
  - HNSW  
  - HCNNG  
  - pyNNDescent
- **Graph-based indices** suitable for high-dimensional ANN search
- **Parallel execution** using ParlayLib primitives for scalability
- **Range search support** via algorithms from the paper *Range Retrieval with Graph-Based Indices*
- **Tools for algorithm design**: utilities and data tools to help design and experiment with ANN algorithms
- **C++ implementation** for performance and low-level control
- **Python directory** present in the repo, indicating Python-related bindings or tooling
- **Build system support**  
  - CMake configuration (`CMakeLists.txt`)  
  - Bazel configuration (`WORKSPACE`, `.bazelrc`)

## Technology Stack
- Language: C++ (with associated Python directory)  
- Parallel library: ParlayLib  
- Focus: Graph-based approximate nearest neighbor and range search in high dimensions

## Use Cases
- Core similarity search component in vector databases
- Large-scale vector retrieval and recommendation systems
- Research and experimentation on graph-based ANN algorithms

## Pricing
ParlayANN is an open-source library. No pricing plans are specified; usage terms are governed by the license provided in the repository (`LICENSE`).