# IVF (Inverted File Index)

**Category:** Concepts & Definitions  
**Also known as:** IVF index, Inverted File, IVF-Flat (in FAISS)  
**Ecosystem / Brand Example:** FAISS

---

## Overview

IVF (Inverted File Index) is an indexing technique commonly used in vector databases and similarity search libraries (such as FAISS) to speed up Approximate Nearest Neighbor (ANN) search. 

Instead of scanning all vectors, IVF clusters vectors into multiple partitions (often called *inverted lists* or *cells*). At query time, only a subset of the most relevant partitions is searched, reducing the number of distance computations and improving query latency on large datasets.

---

## Key Idea

1. **Cluster the vector space** into a fixed number of partitions (e.g., using k-means).  
2. **Assign each vector** to the nearest cluster; each cluster is stored as an inverted list.  
3. **At query time**, locate the closest clusters to the query vector and only search within those selected lists.

This trades a small amount of accuracy for big gains in speed and scalability.

---

## Features

- **Partitioned Index Structure**  
  - Vectors are grouped into multiple inverted lists (partitions/cells).  
  - Each list corresponds to a centroid in the clustered vector space.

- **Approximate Nearest Neighbor (ANN) Support**  
  - Designed for approximate, not exact, nearest neighbor search.  
  - Accuracy vs. speed can be tuned via configuration (e.g., number of probed lists).

- **Efficient Query-Time Probing**  
  - Only a small subset of partitions is scanned per query.  
  - Reduces the number of distance computations compared to a flat (brute-force) index.

- **Scalability to Large Datasets**  
  - Suitable for millions to billions of vectors.  
  - Partitioning keeps per-query work manageable even as the dataset grows.

- **Configurable Number of Partitions**  
  - The number of inverted lists (e.g., `nlist` in FAISS) can be tuned.  
  - More partitions can improve speed at the cost of index-building complexity.

- **Configurable Search Breadth**  
  - The number of lists probed at query time (e.g., `nprobe`) can be adjusted.  
  - Higher `nprobe` typically improves recall but increases latency.

- **Compatible with Other Compression Schemes**  
  - IVF can be combined with vector compression methods (e.g., Product Quantization) for memory efficiency.  
  - Common variants include IVF-Flat, IVF-PQ, etc.

- **Integration in Vector Databases and Libraries**  
  - Widely used in libraries like FAISS and in many vector database backends.  
  - Serves as a backbone index type for similarity search services.

- **Improved Latency vs. Flat Indexes**  
  - Compared to a flat index that compares a query to every vector, IVF significantly reduces query time on large collections.  
  - Particularly beneficial for real-time or near-real-time semantic search and recommendation workloads.

---

## Typical Use Cases

- Semantic search over large document or embedding collections.
- Recommendation systems using user/item embeddings.
- Image, audio, or video similarity search with high-dimensional feature vectors.
- Any ANN workload where dataset size makes brute-force search impractical.

---

## Pricing

IVF is an *indexing concept/technique*, not a standalone product or service, so there is no direct pricing. Costs, if any, come from the specific database or library implementation (e.g., FAISS-based services) rather than the IVF method itself.