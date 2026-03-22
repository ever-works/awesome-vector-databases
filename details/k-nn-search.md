## Overview

k-Nearest Neighbors (k-NN) search is the fundamental operation underlying vector search and similarity-based retrieval. Given a query vector, k-NN finds the k most similar vectors in a dataset according to a distance metric.

## Types of k-NN Search

### Exact k-NN
- Computes distance to all vectors
- Guarantees finding true k nearest neighbors
- O(n) complexity for n vectors
- Practical only for small datasets (<100K vectors)

### Approximate k-NN (ANN)
- Uses indexing structures (HNSW, IVF, etc.)
- Trades some accuracy for massive speed gains
- Typical 95%+ recall with 100x+ speedup
- Essential for large-scale applications

## Key Parameters

### k Value
- Number of neighbors to return
- Typical values: 1-100
- Higher k = more context but slower
- Application-dependent choice

### Distance Metric
- Cosine similarity (most common for embeddings)
- Euclidean distance (L2)
- Dot product / inner product
- Manhattan distance (L1)

## Applications

- **Semantic Search**: Finding similar documents
- **Recommendation Systems**: Similar items or users
- **Image Retrieval**: Visually similar images
- **Anomaly Detection**: Finding outliers
- **Classification**: Label based on neighbors
- **Clustering**: Grouping similar data

## Algorithm Families

### Graph-Based
- HNSW (Hierarchical Navigable Small World)
- NSW (Navigable Small World)
- NSG (Navigable Spread-out Graph)
- DiskANN/Vamana

### Tree-Based
- KD-trees
- Ball trees
- Annoy (Approximate Nearest Neighbors Oh Yeah)

### Hash-Based
- Locality-Sensitive Hashing (LSH)
- Random projection trees

### Clustering-Based
- IVF (Inverted File Index)
- Product Quantization
- FAISS variants

## Trade-offs

**Exact k-NN**:
- ✓ 100% recall
- ✗ Slow for large datasets
- ✗ Not scalable

**Approximate k-NN**:
- ✓ Fast (100x-1000x speedup)
- ✓ Scalable to billions of vectors
- ✗ <100% recall (typically 95-99%)
- ✗ Requires index building

## Implementation

All vector databases implement k-NN:
- Pinecone, Weaviate, Qdrant
- Elasticsearch, OpenSearch
- PostgreSQL (pgvector)
- Standalone libraries (FAISS, Annoy)

## Pricing

Core functionality; available across all platforms.