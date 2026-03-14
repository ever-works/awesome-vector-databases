## Overview

Hierarchical Navigable Small World (HNSW) is a graph-based algorithm that performs approximate nearest neighbor searches (ANN) in vector databases. HNSW is among the top-performing indexes for vector similarity search.

## Core Concepts

HNSW builds upon two fundamental concepts:

1. **Navigable Small World (NSW) graphs**: Creates proximity graphs with both long-range and short-range links, reducing search times to logarithmic complexity

2. **Skip lists**: Borrows the concept of maintaining multiple layers, where HNSW uses layers of NSW graphs instead of linked lists

## Architecture

Hierarchical NSW incrementally builds a multi-layer structure:
- **Top layers**: Longest links for rapid coarse navigation
- **Bottom layers**: Shortest links for fine-grained search
- Each layer contains a proximity graph for nested subsets of elements

## Search Process

1. Start at the top layer with longest links
2. Greedily navigate to closest neighbors
3. Descend through layers progressively
4. Reach bottom layer for final precise search

## Performance Characteristics

- **Time Complexity**: (poly/)logarithmic search times
- **Accuracy**: High recall rates (>95%)
- **Scalability**: Handles billions of vectors
- **Benchmark Performance**: Among best performers in ANN benchmarks

## Advantages

- Excellent balance of speed and accuracy
- Incremental index construction
- No training required (unlike IVF methods)
- Supports dynamic updates (insertions/deletions)
- Robust performance across different datasets

## Trade-offs

- **Memory Overhead**: Requires storing graph structure
- **Index Size**: Larger than compressed alternatives like PQ
- **Build Time**: Can be slower than simpler methods for small datasets

## Implementations

- hnswlib (C++/Python)
- FAISS
- Milvus
- Qdrant
- Weaviate
- Elasticsearch
- Most modern vector databases

## Research Foundation

**Original Paper**: "Efficient and robust approximate nearest neighbor search using Hierarchical Navigable Small World graphs" (Malkov & Yashunin, 2016)

ArXiv: https://arxiv.org/abs/1603.09320

## Use Cases

- Semantic search
- Recommendation systems
- Image similarity search
- LLM applications with RAG
- Real-time vector search

## Pricing

Open algorithm implemented in various databases, no licensing cost.