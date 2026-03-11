## Overview

IVF (Inverted File Index) is a cluster-based approach to approximate nearest neighbor search that partitions the vector space into cells using k-means clustering. During search, only a subset of cells are examined, dramatically reducing computation.

## How IVF Works

1. **Clustering**: Uses k-means to partition vectors into multiple regions (Voronoi Cells)
2. **Inverted Index**: Records vectors within each region
3. **Query**: Search restricted to few regions closest to query vector
4. **Efficiency**: Significantly reduces search space

## Characteristics

- **Cluster-Based**: Divides space into manageable partitions
- **Scalable**: Handles large datasets efficiently
- **Configurable**: Number of clusters and probes tunable
- **Memory Efficient**: Only searches relevant clusters
- **Widely Used**: Proven since 1990s

## Variants

- **IVF-Flat**: Basic IVF without compression
- **IVF-PQ**: IVF with Product Quantization for compression
- **IVF-HNSW**: Combines IVF clustering with HNSW graph

## Performance Trade-offs

- **Speed vs Accuracy**: More clusters = faster search but may miss results
- **nprobe Parameter**: Controls number of clusters searched
- **Build Time**: K-means clustering during index creation

## Use Cases

- Large-scale vector search
- Memory-constrained environments
- Applications where slight accuracy reduction is acceptable
- Systems requiring configurable speed/accuracy trade-offs

## Vector Database Support

Supported by major vector databases:
- FAISS
- Milvus
- Weaviate
- Qdrant

## Comparison

- **vs HNSW**: Lower memory, slightly lower accuracy
- **vs Flat**: Much faster, slight accuracy trade-off
- **vs DiskANN**: Better for in-memory scenarios