---
title: PilotANN
slug: pilotann
url: https://github.com/ytgui/PilotANN
category: sdks-libraries
featured: false
brand: ""
brand_logo_url: "/"
tags:
  - gpu-acceleration
  - ann
  - high-performance

summary: |
  PilotANN is a memory-bounded, GPU-accelerated framework for graph-based approximate nearest neighbor (ANN) vector search, intended as a high-performance engine or component for large-scale vector databases and vector search systems.

features:
  - Memory-bounded GPU acceleration designed specifically for large-scale vector search workloads.
  - Focus on graph-based approximate nearest neighbor (ANN) search.
  - Suitable as a high-performance engine/component within vector databases and vector search pipelines.
  - Implementation built on top of LibTorch (PyTorch C++ backend).
  - Integrates with a FAISS (Facebook AI Similarity Search) build within the same Python environment.
  - Python bindings via setup.py for development (`python3 ./setup.py develop`).
  - Benchmark scripts for evaluating performance on multiple datasets (e.g., `laion-1m`, `laion-100m`).
  - Configurable benchmark parameters such as dataset choice, sample ratio, and principal dimension (`d_principle`).
  - Support for multi-CPU execution with OpenMP thread limiting (`OMP_THREAD_LIMIT`).
  - Example dataset directory structure for deep and LAION datasets (deep-1m, deep-100m, laion-100m).

technical_requirements:
  - Linux environment (instructions provided for RHEL/CentOS-like systems).
  - CUDA-capable NVIDIA GPU with CUDA Toolkit 11.8 and appropriate NVIDIA driver.
  - Python environment (e.g., Anaconda/Miniconda) with Python 3.10.
  - PyTorch 2.1.2 with CUDA 11.8, torchvision, torchaudio, and numpy.
  - Build tools and libraries: CMake, Git, SWIG, LAPACK and LAPACK-devel, compiler toolchain (Development Tools group on RHEL/CentOS).
  - FAISS 1.8.0 built with Python bindings (GPU disabled in the provided example build config).

usage:
  - Build FAISS under the active Python environment, then build and develop-install PilotANN via `python3 ./setup.py develop`.
  - Prepare datasets under a `.datasets/` directory following the documented structure.
  - Run benchmarks using `script/bench_1.py` with options for dataset name, sample ratio, and principal dimension; control CPU parallelism via `OMP_THREAD_LIMIT`.

pricing: |
  PilotANN is an open-source project hosted on GitHub; no pricing information or paid plans are specified in the repository content.

notes: |
  The repository README focuses on build, environment, and benchmarking instructions. Detailed internal algorithm descriptions, API reference, and configuration options beyond the benchmark script parameters are not included in the provided content.
---