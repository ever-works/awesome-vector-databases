## Overview

Hybrid search typically combines BM25 for sparse (keyword-based) retrieval with embeddings from models such as Sentence Transformers or OpenAI embeddings for dense (semantic) retrieval. The formula: Hybrid Search RAG = BM25 (keywords) + Vectors (semantic) + Reranking (precision).

## Key Components

### BM25 (Keyword Search)
The BM25 (Best Match 25) algorithm is a popular and effective ranking function employed for keyword matching. BM25's role is to ensure exact keyword matches and term rarity are prioritized.

### Vector Search
Semantic vector search uses high-dimensional embeddings and approximate nearest neighbor (ANN) algorithms (e.g., HNSW) to retrieve conceptually similar documents regardless of exact term overlap.

### Reranking
Reranking takes results from different search methods and reorders them based on additional processing using the content of the documents, not just the scores. This step significantly improves precision.

## Fusion Methods

### Reciprocal Rank Fusion (RRF)
RRF provides a way to merge rankings from semantic and token-based search results. It assigns scores based on how high each document ranks in both keyword and vector searches.

In practice, RRF is the best starting point for hybrid search because of its simplicity and resilience to mismatched score scales.

## Implementation Frameworks

Common frameworks for hybrid search in RAG:
- **LangChain**: Easily combine vector and keyword retrievers in custom pipelines
- **LlamaIndex**: Integrates structured and unstructured data for better retrieval
- **Haystack**: Built-in support for hybrid retrievers with flexible ranking and evaluation

## Production Best Practices

- Start with RRF for fusion due to its simplicity
- Tune BM25 and vector weights based on your use case
- Use reranking models for final precision improvements
- Monitor both keyword and semantic recall separately
- Consider query complexity when balancing components