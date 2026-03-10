## Overview

IVF-FLAT (Inverted File Index with Flat vectors) enhances search efficiency by using K-means clustering to partition high-dimensional vectors into multiple regions, narrowing the search area through neighbor partitions.

## How It Works

1. **Training Phase**:
   - Apply K-means clustering to vector space
   - Create centroids representing each cluster
   - Assign vectors to nearest centroid

2. **Search Phase**:
   - Find nearest centroids to query vector
   - Search only vectors in those partitions
   - Return top-k most similar vectors

## Key Parameters

- **nlist**: Number of clusters/partitions
- **nprobe**: Number of clusters to search (trade-off: speed vs. accuracy)
- Higher nprobe → better recall, slower search
- Lower nprobe → faster search, lower recall

## Advantages

- Faster than exhaustive search
- Scalable to millions of vectors
- Simple and proven approach
- Good accuracy-speed trade-off
- Widely supported

## Disadvantages

- Requires training phase
- All vectors still stored in full precision
- Memory intensive for large datasets
- Less efficient than compressed alternatives (IVF-PQ)

## Comparison with Other Indexes

- **vs. FLAT**: Much faster, slightly lower recall
- **vs. IVF-PQ**: Higher accuracy, more memory
- **vs. HNSW**: Less memory, slower queries
- **vs. DiskANN**: In-memory only

## Use Cases

- Medium-scale datasets (millions of vectors)
- When memory is available
- Applications requiring good recall
- Balance of speed and accuracy

## Tuning Guidelines

- Start with nlist = sqrt(N) where N is dataset size
- Adjust nprobe based on recall requirements
- Monitor memory usage
- Benchmark against workload

## Database Support

- Milvus
- FAISS
- Weaviate
- Qdrant
- Most major vector databases

## Performance Characteristics

- Training: O(N * K) where K is number of iterations
- Search: O(nprobe * vectors_per_cluster)
- Memory: O(N * D) where D is dimensions