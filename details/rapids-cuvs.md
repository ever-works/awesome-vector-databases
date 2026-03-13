## Overview

cuVS is a library dedicated to Vector Search on the GPU that provides approximate nearest neighbors and clustering algorithms essential for modern vector search libraries. The cuVS library leverages the RAPIDS RAFT library, which provides accelerated building blocks for composing machine learning and data analytics on GPU.

## Key Capabilities

Leveraging the cuVS library, vector search operations achieve unmatched speed by delivering:
- Better index build times
- Higher throughput
- Lower latency at every level of recall

cuVS exploits the parallel architecture of NVIDIA GPUs, allowing for deployment of complex algorithms like IVF-PQ, IVF-flat, and CAGRA.

## Performance Benefits

Faiss integration of cuVS offers:
- Up to 12x acceleration on GPU for faster index builds
- Up to 4.7x improvement in real-time search with lower search latency
- CAGRA achieves high throughput in batch scenarios—serving millions of queries per second
- Outperforms CPU-based HNSW across both datasets

## Integrations and Availability

cuVS has APIs for:
- C
- C++
- Python
- Rust

Integrated into:
- FAISS
- Milvus
- Several other vector databases

## Applications

GPU-accelerated vector search can take large machine learning and natural language processing workflows from hours to near real-time speeds, enabling:
- Hybrid search
- Anomaly detection
- Large-scale similarity search
- Real-time recommendations

## Pricing

Free and open-source C++ library.