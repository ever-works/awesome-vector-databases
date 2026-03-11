## Overview

Reranking is a two-stage retrieval pattern that significantly improves RAG accuracy. Fast initial retrieval gets candidates, then a sophisticated reranker provides precise final rankings.

## Why Reranking?

Initial retrieval prioritizes speed and recall:
- **Bi-encoders**: Fast but less accurate
- **BM25**: Good for keywords but misses semantics

Rerankers prioritize precision:
- **Cross-encoders**: Slow but highly accurate
- **ColBERT**: Balance of speed and accuracy

## Standard Pipeline (2026)

1. **Initial Retrieval**: Get top-100 to 200 candidates
   - Vector search (dense embeddings)
   - Keyword search (BM25)
   - Fused via RRF

2. **Reranking**: Re-score top-k candidates
   - Cross-encoder models (BGE, Cohere)
   - ColBERT MaxSim
   - Return top-N final results

## Performance Impact

Reranking delivers 15-40% higher retrieval accuracy and more relevant results compared to embeddings alone.

## Popular Rerankers

- **Cohere Rerank**: API-based, 100+ languages
- **BGE Reranker**: Open-source, self-hostable
- **ColBERT**: Late interaction, fast
- **Jina ColBERT v2**: Multilingual, token-level
- **Mixedbread**: Code-optimized

## Cost vs Quality Trade-offs

### High Quality
- Cohere Rerank 3.5
- Cross-encoder rerankers
- Best accuracy, higher API costs

### Balanced
- BGE reranker (self-hosted)
- ColBERT models
- Good accuracy, lower cost

### Fast
- Smaller reranker models
- Lower latency, slight accuracy trade-off

## Implementation Pattern

```
top_100 = vector_search(query) + bm25_search(query)
fused = rrf(top_100)
top_10 = reranker(query, fused[:50])
return top_10
```

## When to Use

- Production RAG systems
- High-value queries
- Accuracy-critical applications
- Multi-source retrieval
- Hybrid search systems

## When to Skip

- Simple use cases
- Budget constraints
- Latency requirements <50ms
- Small candidate sets

## Best Practices

- Retrieve more initially (100-200)
- Rerank subset (20-50)
- Return final top-k (5-10)
- Monitor latency vs accuracy
- Test different rerankers
- Consider self-hosting for cost

## 2026 Standard

Reranking has become standard in production RAG systems, with most frameworks supporting it out of the box.