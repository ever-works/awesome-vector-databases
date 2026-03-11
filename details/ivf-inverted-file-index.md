## Overview

IVF (Inverted File Index) partitions the vector space into clusters (Voronoi cells) using k-means, enabling fast approximate search by checking only relevant clusters.

## How It Works

1. **Cluster vectors**: K-means creates centroids
2. **Assign to clusters**: Each vector assigned to nearest centroid
3. **Build inverted lists**: Vectors grouped by cluster
4. **Query**: Find nearest centroids, search their lists

## Variants

- **IVF-FLAT**: No compression, exact distances within clusters
- **IVF-PQ**: Product Quantization for compression
- **IVF-SQ**: Scalar Quantization variant

## Parameters

- **nlist**: Number of clusters
- **nprobe**: Clusters to search at query time

## Advantages

- Fast search through pruning
- Memory efficient (with PQ)
- Scalable to large datasets
- Good recall-speed balance

## Used In

- FAISS
- Milvus
- pgvector
- LanceDB

## Pricing

Open algorithm.