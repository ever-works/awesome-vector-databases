## Overview

Reciprocal Rank Fusion (RRF) is a method for combining results from multiple ranking systems by computing the reciprocal of ranks. It's commonly used in hybrid search to merge dense vector search results with sparse keyword search (BM25) results.

## How RRF Works

For each document across all result lists, compute:
- RRF_score = Σ 1 / (k + rank_i)
- Where k is typically 60
- rank_i is the document's rank in the i-th result list

## Advantages

### No Training Required

- No training data needed
- No parameter tuning (beyond k)
- Works out-of-the-box

### Robust Performance

- Handles varying numbers of results per system
- Works with different scoring scales
- Performs well across diverse queries

## Common Applications

### Hybrid Search

Combining:
- Dense embeddings (semantic search)
- Sparse vectors (keyword/BM25 search)
- Produces better results than either alone

### Multi-Stage Retrieval

Merging results from:
- Different embedding models
- Various indexing strategies
- Multiple data sources

## Use Cases

- Hybrid semantic + keyword search
- Multi-model ensemble retrieval
- Combining dense and sparse retrievers in RAG
- E-commerce product search

## Pricing

Implemented in open-source search engines (OpenSearch, Elasticsearch, Weaviate, etc.)