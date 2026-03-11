## Overview

Reranking models refine initial retrieval results by computing precise relevance scores between queries and retrieved documents.

## Architecture

### Cross-Encoders

- Process query and document together
- More accurate than bi-encoders
- Expensive: Can't pre-compute
- Applied to top-k results only

## Popular Models

- **Cohere Rerank**: Commercial API
- **bge-reranker-v2-m3**: BAAI multilingual reranker
- **Cross-Encoder Models**: HuggingFace Sentence Transformers
- **Jina Reranker**: Various sizes available

## Typical Pipeline

1. **Retrieval**: Get top-100 candidates with vector search
2. **Rerank**: Apply reranker to refine order
3. **Select**: Choose top-10 for LLM context

## Benefits

- **Improved Precision**: Better relevance ranking
- **Better RAG**: More relevant context for LLMs
- **Hybrid Approach**: Combine speed (retrieval) + accuracy (reranking)

## When to Use

- High-precision requirements
- When latency allows (~100ms)
- Production RAG systems
- Search quality matters

## Pricing

- **Open Source**: Free (bge-reranker, others)
- **Cohere Rerank**: Usage-based API pricing
- **Self-hosted**: Compute costs