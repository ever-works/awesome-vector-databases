## Overview

cuVS is a GPU-accelerated library for vector search and clustering from NVIDIA RAPIDS. Enables databases to scale up and out for massive-scale vector search workloads, delivering unmatched speed through GPU acceleration.

## Performance Benefits

### Index Building
- **12x faster** index building on GPU at 95% recall (vs. CPU)
- Massive speedups for large datasets
- Parallel processing on GPU architecture

### Query Performance
- **8x lower** search latencies at 95% recall
- Higher throughput at all recall levels
- Better latency characteristics

### Integration Performance
- Faiss integration: 12x faster builds, 8x lower latency
- Milvus on GPU: Significant speedups with cuVS
- Production-grade performance improvements

## Supported Algorithms

- **IVF-PQ**: Inverted File with Product Quantization
- **IVF-Flat**: Inverted File with flat vectors
- **CAGRA**: CUDA-Accelerated Graph-based ANN
- **HNSW**: Hierarchical Navigable Small World
- **Brute Force**: Exact search option

## Multi-Language Support

- **C**: Native C API
- **C++**: Modern C++ interface
- **Python**: Python bindings
- **Rust**: Rust bindings

## CPU-GPU Interoperability

- Build index on GPU, search on CPU
- Flexible deployment options
- Hybrid architectures supported
- Optimal resource utilization

## Key Features

- Fully open source on GitHub
- Part of NVIDIA RAPIDS ecosystem
- Production-ready and battle-tested
- Continuous optimization and updates
- Enterprise support available

## Use Cases

### Real-Time Applications
- Machine learning workflows (hours to near real-time)
- Natural language processing at scale
- Hybrid search systems
- Anomaly detection

### Database Integration
- Vector database acceleration
- In-database GPU processing
- Distributed search systems
- Cloud-native deployments

## Integration

### Faiss
- Enhanced GPU-accelerated Faiss
- Drop-in performance improvements
- Maintained compatibility

### Milvus
- Native cuVS integration
- GPU-accelerated vector search
- Supercharged performance

### Custom Applications
- Direct API access
- Embeddable in applications
- Flexible architecture

## Technical Architecture

- Exploits parallel GPU architecture
- Optimized CUDA kernels
- Memory-efficient implementations
- Scalable to multiple GPUs

## GPU Requirements

- NVIDIA GPU with CUDA support
- Compute Capability 7.0+ recommended
- Sufficient GPU memory for workload
- CUDA Toolkit installation

## Installation

### Conda (Recommended)
```bash
conda install -c rapidsai -c conda-forge cuvs
```

### From Source
```bash
git clone https://github.com/rapidsai/cuvs
```

## Documentation

- Comprehensive API documentation
- Example notebooks and tutorials
- Performance tuning guides
- Integration examples

## RAPIDS Ecosystem

Part of NVIDIA RAPIDS suite:
- cuDF: GPU DataFrames
- cuML: GPU Machine Learning
- cuGraph: GPU Graph Analytics
- cuVS: GPU Vector Search

## Performance Considerations

- Optimal for large-scale workloads
- GPU memory vs. dataset size
- Batch size optimization
- Multi-GPU scaling

## Community and Support

- GitHub: rapidsai/cuvs
- RAPIDS community forums
- NVIDIA developer resources
- Enterprise support available

## Pricing

Free and open-source under Apache 2.0 license. No licensing costs. GPU hardware required.