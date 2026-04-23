# ScaNN

ScaNN (Scalable Nearest Neighbors) is Google Research's library for efficient high-dimensional vector similarity search.

## Disk Persistence vs In-Memory

Optimized quantization reduces memory footprint, supporting disk-persistent deployments for datasets beyond RAM. Enables out-of-core search in large-scale setups unlike memory-intensive HNSW without compression.

## Key Features

- Asymmetric and anisotropic vector quantization
- High-throughput MIPS
- Up to 2x faster than benchmarks at same accuracy
- TensorFlow/Numpy support

## Use Cases

- Billion-scale embedding retrieval
- Production recommendation systems
- Compressed large vector collections

## Comparisons

**DiskANN vs HNSW**: ScaNN focuses on quantization for speed/accuracy trade-off, complementing graph indexes like DiskANN (graph+quantization) and outperforming uncompressed HNSW in compressed disk scenarios.

## Pricing

Open-source, free.