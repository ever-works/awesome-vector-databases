## Overview

IVF-FLAT (Inverted File with FLAT vectors) is an indexing method that partitions the vector space into clusters, with each cluster having a centroid. Vectors are stored in their original, uncompressed form (FLAT) within their assigned clusters.

## How IVF-FLAT Works

### Indexing Process

1. **Clustering**: Partition vectors into clusters using k-means or similar algorithm
2. **Centroid Creation**: Create a centroid for each cluster
3. **Assignment**: Assign each vector to its nearest cluster
4. **Storage**: Store full-precision vectors within clusters

### Search Process

1. Find nearest cluster centroids to query vector
2. Search only within selected clusters
3. Compare query with full-precision vectors in those clusters
4. Return top-k most similar vectors

## Characteristics

### Accuracy

Higher accuracy than IVF-PQ because:
- Stores full-precision vectors (no quantization loss)
- Exact distance calculations within searched clusters

### Memory Usage

Higher memory usage than IVF-PQ:
- Stores complete vectors instead of compressed codes
- Suitable when memory is not the primary constraint

## Trade-offs

**vs IVF-PQ**:
- Higher accuracy, higher memory usage
- Slower than IVF-PQ due to full-precision comparisons

**vs HNSW**:
- Lower memory for index structure
- Can be slower for high-recall scenarios

## Configuration Parameters

- **nlist**: Number of clusters
- **nprobe**: Number of clusters to search (recall vs speed trade-off)

## Use Cases

- Applications requiring high accuracy
- When memory is available
- Medium-scale datasets (millions of vectors)
- Scenarios where some recall loss is acceptable

## Pricing

Implemented in open-source libraries (FAISS, Milvus, etc.)