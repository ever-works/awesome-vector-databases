## Overview

IVF-PQ (Inverted File with Product Quantization) is a vector indexing method that combines two techniques: inverted file indexing for efficient search space reduction and product quantization for memory-efficient vector storage.

## How It Works

### Inverted File (IVF)
- Partitions the vector space into clusters
- Creates an inverted index mapping clusters to vectors
- During search, only relevant clusters are examined

### Product Quantization (PQ)
- Divides vectors into subvectors
- Quantizes each subvector independently
- Dramatically reduces memory footprint

## Storage Efficiency

For 128-dimensional vectors divided into 32 subvectors:
- Original storage: 128 × 4 bytes = 512 bytes
- IVF-PQ storage: 32 × 1 byte = 32 bytes
- Compression ratio: 1/16th of original size

## Performance Characteristics

ScaNN (which builds upon IVF-PQ) achieves:
- 5x QPS improvement over IVFFLAT on Cohere1M dataset
- 6x QPS improvement over basic IVF-PQ
- Maintains high recall rates with compressed vectors

## Relationship to ScaNN

ScaNN is based on the IVF-PQ framework but introduces key optimizations:
- Score-aware quantization loss
- Anisotropic loss functions
- SIMD in-register lookup tables

## Applications

- Large-scale vector search with memory constraints
- Balancing search speed and memory usage
- Systems requiring high throughput with limited resources

## Trade-offs

- Reduces memory usage significantly
- Slight reduction in recall compared to exact search
- Faster than exact search but slower than some graph-based methods