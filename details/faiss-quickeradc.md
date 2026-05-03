# faiss-quickeradc

## Overview
faiss-quickeradc extends FAISS with Quicker ADC for accelerated product-quantization ANN search on GPUs via CUDA.

## Features
- CUDA-accelerated distance computations using SIMD shuffle instructions
- Faster encoding/decoding for PQ indices
- Integration with FAISS GPU stack
- C/C++/Python APIs

## Use Cases
- Real-time AI recommendations
- CV inference pipelines
- High-throughput similarity search in GPU clusters

## Comparisons
- Significantly faster ADC than CPU Faiss
- GPU acceleration provides 10-100x speedup over CPU Faiss baselines
- Better throughput than standard GPU Faiss PQ

## Pricing
Free open-source (check repo license).