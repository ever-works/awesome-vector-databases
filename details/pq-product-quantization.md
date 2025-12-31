---
title: "PQ (Product Quantization)"
slug: "pq-product-quantization"
brand: "faiss"
brand_logo_url: "https://faiss.ai/images/faiss_logo_black.svg"
category: "concepts-definitions"
featured: false
tags:
  - quantization
  - ann
  - vector-compression
images:
  - "https://faiss.ai/images/pq.png"
source_url: "https://cybergarden.au/blog/5-powerful-vector-database-tools-2025"
---

## Overview

**PQ (Product Quantization)** is a vector compression and indexing technique commonly used in vector databases and similarity search libraries (such as Faiss). It enables efficient approximate nearest neighbor (ANN) search by splitting high-dimensional vectors into multiple subspaces and quantizing each subspace separately. This allows large-scale embedding collections to be stored compactly while still supporting fast semantic search.

## Key Idea

Instead of storing full-precision vectors, Product Quantization:
- Divides each original vector into smaller, disjoint sub-vectors (subspaces).
- Learns a separate codebook (set of centroids) for each subspace.
- Represents each sub-vector by the index of its nearest centroid in the corresponding codebook.

The resulting compressed representation significantly reduces memory usage while preserving enough structure for efficient ANN search.

## Features

- **Vector splitting into subspaces**  
  High-dimensional vectors are partitioned into multiple lower-dimensional blocks, enabling independent quantization of each part.

- **Subspace quantization (codebooks)**  
  Each subspace has its own learned codebook of centroids; sub-vectors are approximated by the nearest centroid index.

- **Compact embedding storage**  
  Full-precision floats are replaced with short integer codes, reducing RAM and disk footprint for large collections of embeddings.

- **Efficient approximate nearest neighbor (ANN) search**  
  Distance computations are performed in the compressed space using precomputed lookup tables, enabling fast similarity search over millions or billions of vectors.

- **Speed–accuracy trade-off control**  
  The number of subspaces, centroids per subspace, and code size can be tuned to balance search accuracy against memory usage and query latency.

- **Compatibility with vector indexes**  
  Often combined with other ANN indexing techniques (e.g., IVF, HNSW in systems like Faiss) to further improve search performance at scale.

- **Scalability to large datasets**  
  Designed to support very large vector collections by minimizing per-vector storage, making it practical to keep massive embedding sets in memory or on fast storage.

- **Support for semantic search use cases**  
  Well-suited for applications that rely on embedding similarity (e.g., text, image, or multimodal search) where exact nearest neighbor search would be too expensive.

## Use Cases

- Large-scale semantic search over text, images, or documents.
- Vector databases powering LLM-based retrieval, RAG, and recommendation.
- Any scenario requiring memory-efficient storage of high-dimensional embeddings with fast ANN queries.

## Pricing

Product Quantization (PQ) is a **technique/concept**, not a standalone commercial product, so there is no pricing model associated with it directly. Pricing depends on the specific database or library (e.g., Faiss or a managed vector database) in which PQ is implemented.