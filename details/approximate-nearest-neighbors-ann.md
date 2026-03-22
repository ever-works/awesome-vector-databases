## Overview

Approximate Nearest Neighbor (ANN) search is a family of algorithms that find nearest neighbors with high probability while being orders of magnitude faster than exact search. ANN is essential for large-scale vector search applications.

## Why ANN?

Exact nearest neighbor search has O(n×d) complexity:
- n = dataset size
- d = vector dimensions
- Impractical for >1M vectors

## ANN achieves O(log n) or better by:
- Building specialized index structures
- Searching a subset of the dataset
- Accepting near-perfect (95-99%) recall

## Major ANN Approaches

### Graph-Based Methods
**HNSW (Hierarchical Navigable Small World)**
- Most popular ANN algorithm
- Excellent recall-speed trade-off
- Fast queries, moderate build time
- Used in: Weaviate, Qdrant, Milvus

**DiskANN/Vamana**
- SSD-optimized graph index
- Billion-scale capability
- Used in: Azure Cosmos DB, PostgreSQL

### Clustering-Based Methods
**IVF (Inverted File Index)**
- Partitions space into clusters
- Fast for very large datasets
- Used in: Pinecone, FAISS

**IVF-PQ (with Product Quantization)**
- Combines clustering + compression
- Memory-efficient
- Used in: FAISS, Milvus

### Tree-Based Methods
**Annoy (Approximate Nearest Neighbors Oh Yeah)**
- Random projection trees
- Memory-efficient
- Created by Spotify

**KD-trees / Ball trees**
- Classical spatial data structures
- Less effective in high dimensions

### Hash-Based Methods
**LSH (Locality-Sensitive Hashing)**
- Hash similar items to same buckets
- Sublinear query time
- Good for very high dimensions

## Key Metrics

### Recall
Fraction of true nearest neighbors found:
- 100% = exact search
- 95-99% = typical ANN target
- 90% = fast but lower quality

### Queries Per Second (QPS)
- Throughput measure
- Higher is better
- Depends on recall target

### Build Time
- Time to create index
- One-time cost
- Varies widely by algorithm

## Recall-Speed Trade-off

All ANN algorithms allow tuning:
- Higher recall → slower queries
- Lower recall → faster queries
- Configure per application needs

Example HNSW parameters:
- ef_search: controls search quality
- Higher ef_search = better recall, slower

## Benchmarking

**ANN-Benchmarks.com**
- Standard comparison framework
- Tests algorithms on real datasets
- Shows recall vs QPS curves

**Key findings**:
- HNSW: best overall
- ScaNN: strong for specific configs
- IVF-PQ: memory-constrained scenarios

## Choosing an ANN Algorithm

Consider:
- Dataset size (millions vs billions)
- Query latency requirements
- Memory constraints
- Update frequency
- Recall requirements

## Pricing

Core technology; implementations vary by platform.