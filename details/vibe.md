## Overview

VIBE (Vector Index Benchmark for Embeddings) is an extensible benchmark for approximate nearest neighbor search methods, or vector indexes, using modern embedding datasets. It addresses the limitations of existing benchmarks like ANN-Benchmarks by focusing on contemporary embedding models characteristic of modern applications.

## Key Features

- **Modern Embedding Datasets**: Includes datasets based on modern embedding models rather than outdated representations like raw pixels or SIFT descriptors
- **In-Distribution and Out-of-Distribution**: Contains datasets for both in-distribution (6 datasets) and out-of-distribution (6 datasets) evaluation scenarios
- **Comprehensive Algorithm Coverage**: Benchmarks 21 state-of-the-art vector index implementations
- **Quantization Support**: Supports quantized datasets in both 8-bit integer and binary precision formats
- **HPC Environment Support**: Includes support for high-performance computing environments with Slurm and NUMA
- **Extensible Pipeline**: Provides a pipeline for creating benchmark datasets using dense embedding models

## Scope and Evaluation

VIBE conducted a comprehensive evaluation of state-of-the-art vector indexes, testing:
- 21 different implementations
- 12 in-distribution datasets
- 6 out-of-distribution datasets

## Use Cases

The benchmark is designed for applications such as:
- Retrieval-augmented generation (RAG)
- Semantic search systems
- Modern ML applications using embedding models
- Evaluating vector search algorithms on contemporary datasets

## Resources

- **Website**: Interactive plots and benchmark results at https://vector-index-bench.github.io/
- **GitHub**: https://github.com/vector-index-bench/vibe
- **Datasets**: Available on Hugging Face at vector-index-bench/vibe
- **Publication**: arXiv:2505.17810 (2025)

## Authors

Developed by E. Jääsaari, V. Hyvönen, M. Ceccarello, T. Roos, and M. Aumüller.

## Significance

VIBE represents a significant advancement in vector index benchmarking by using datasets that reflect the actual embedding models deployed in modern AI applications, providing more relevant and actionable performance insights than traditional benchmarks.