## Overview

Vector indexes are data structures that enable fast approximate nearest neighbor (ANN) search. Different index types offer various trade-offs between speed, accuracy, memory, and update capability.

## Index Type Categories

### Graph-Based Indexes

**HNSW (Hierarchical Navigable Small World)**
- **Best For**: General-purpose, high recall
- **Pros**: Excellent speed/accuracy, fast queries
- **Cons**: High memory usage, slow builds
- **Used By**: Weaviate, Qdrant, Milvus
- **Typical Recall**: 95-99% at high speed

**NSW (Navigable Small World)**
- **Best For**: Smaller datasets
- **Pros**: Simpler than HNSW
- **Cons**: Slower than HNSW
- **Used By**: Older implementations

### Clustering-Based Indexes

**IVF (Inverted File)**
- **Best For**: Large datasets, lower memory
- **Pros**: Memory efficient, good for static data
- **Cons**: Slower than HNSW, requires training
- **Used By**: FAISS, Pinecone
- **Parameters**: nlist (clusters), nprobe (search)

**IVF-PQ (Inverted File + Product Quantization)**
- **Best For**: Huge datasets, memory constraints
- **Pros**: 8-64x compression, scalable
- **Cons**: Lower accuracy than non-compressed
- **Used By**: FAISS, Milvus
- **Compression**: Down to 1/64th original size

### Tree-Based Indexes

**Annoy (Approximate Nearest Neighbors Oh Yeah)**
- **Best For**: Read-heavy workloads, static data
- **Pros**: Memory-mapped files, no RAM needed
- **Cons**: Slower than HNSW
- **Used By**: Spotify (legacy), some specialized apps

**KD-Trees / Ball Trees**
- **Best For**: Low dimensions (<20)
- **Pros**: Simple, interpretable
- **Cons**: Ineffective in high dimensions
- **Used By**: Sklearn, traditional ML

### Hash-Based Indexes

**LSH (Locality-Sensitive Hashing)**
- **Best For**: Very high dimensions (>1000)
- **Pros**: Sublinear query time
- **Cons**: Lower accuracy, complex tuning
- **Used By**: Specialized applications

### Disk-Based Indexes

**DiskANN**
- **Best For**: Billion-scale, SSD storage
- **Pros**: Scales beyond RAM, fast
- **Cons**: Requires SSD, complex
- **Used By**: Azure Cosmos DB, pgvectorscale

### Flat (Brute Force)

**Flat Index**
- **Best For**: Small datasets (<10K), 100% recall
- **Pros**: Perfect accuracy, simple
- **Cons**: O(n) search time
- **Used By**: All databases (baseline)

## Comparison Matrix

| Index | Query Speed | Build Time | Memory | Accuracy | Updates |
|-------|-------------|------------|--------|----------|--------|
| HNSW | ⭐⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| IVF | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐ |
| IVF-PQ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ |
| Annoy | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐ |
| DiskANN | ⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐ |
| Flat | ⭐ | ⭐⭐⭐⭐⭐ | ⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |

## Selection Guide

### By Dataset Size

**Small (<100K vectors)**
- Use: Flat or HNSW
- Reason: Simplicity, speed

**Medium (100K-10M vectors)**
- Use: HNSW
- Reason: Best balance

**Large (10M-100M vectors)**
- Use: HNSW or IVF-PQ
- Reason: Performance vs memory

**Huge (>100M vectors)**
- Use: IVF-PQ or DiskANN
- Reason: Scale beyond RAM

### By Use Case

**High Accuracy Critical**
- Use: HNSW (with high ef_search)
- Alternative: Flat (if small enough)

**Memory Constrained**
- Use: IVF-PQ or DiskANN
- Compression essential

**Fast Writes/Updates**
- Use: HNSW
- Avoid: IVF (requires retraining)

**Read-Only, Static**
- Use: Annoy or IVF
- Memory-mapped files

## Key Parameters

### HNSW
- `M`: Links per node (16-64 typical)
- `ef_construction`: Build quality (100-500)
- `ef_search`: Query recall (50-500)

### IVF
- `nlist`: Number of clusters (√n typical)
- `nprobe`: Clusters to search (1-100)

### IVF-PQ
- `nlist`: Cluster count
- `m`: Subvector count (8-64)
- `nbits`: Bits per code (8 typical)

## Hybrid Approaches

Some databases use multiple indexes:
- HNSW + Flat (exact reranking)
- IVF + PQ (clustering + compression)
- HNSW + Quantization (speed + memory)

## Pricing

Index type impacts compute and storage costs.