## Overview
SimSIMD is an open‑source, SIMD‑accelerated library for fast similarity and distance computations on vectors. It targets use cases such as vector search, vector databases, and high‑performance numerical workloads, providing a faster alternative to libraries like `scipy.spatial.distance` and `numpy.inner`.

## Key Capabilities
- Implements dot products and similarity metrics
- Supports multiple numeric types: `f64`, `f32`, `f16`, real & complex, `i8`, and bit vectors
- SIMD acceleration across multiple CPU instruction sets: AVX2, AVX‑512, NEON, SVE, and SVE2
- Achieves large speedups (reported up to ~200x) over naïve or non‑SIMD implementations for inner products and distances
- Designed for integration into vector search and vector database pipelines

## Language & Platform Support
- Core implementation in C / C++ (via `include` and `c` directories)
- Bindings / integrations for multiple languages:
  - Python
  - Rust
  - JavaScript
  - Swift
  - Go (Golang)

## Features
- **SIMD‑Accelerated Operations**  
  - Vector inner products (dot products)  
  - Similarity and distance metrics for numerical vectors  
  - Optimized kernels per CPU architecture (AVX2, AVX‑512, NEON, SVE, SVE2)

- **Data Type Support**  
  - Floating‑point: `f64`, `f32`, `f16`  
  - Real and complex numbers  
  - Integer: `i8`  
  - Bit vectors

- **Multi‑Language Bindings**  
  - Python package for numerical workloads and vector search pipelines  
  - Rust crate for systems and performance‑critical applications  
  - JavaScript bindings for web or Node.js environments  
  - Swift bindings for Apple platforms  
  - Go bindings for Go‑based services

- **Cross‑Platform / Cross‑Architecture Design**  
  - Portable SIMD abstractions targeting multiple CPU instruction sets  
  - Suitable for x86 and ARM ecosystems (via AVX*, NEON, SVE, SVE2)

- **Open‑Source & Integration‑Friendly**  
  - Source available on GitHub  
  - Modular layout with language‑specific folders for easier integration  
  - Apache‑2.0 license for permissive use in open‑source and commercial projects

## License
- **Apache‑2.0**

## Pricing
- SimSIMD is an open‑source library under the Apache‑2.0 license and is free to use. No pricing plans are listed.