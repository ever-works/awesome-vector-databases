## Overview

Reranking is a two-stage retrieval approach where:
1. **First Stage**: Fast retrieval (bi-encoder, BM25) gets top-k candidates (e.g., 100 results)
2. **Second Stage**: Slower but more accurate model reorders these candidates

## Why Reranking?

### Initial Retrieval Limitations
- Bi-encoders: Fast but less accurate
- Encode query and document separately
- Limited interaction between query and document

### Reranker Advantages
- **Cross-Encoders**: Process query-document pairs jointly
- **Better Accuracy**: Captures nuanced relevance signals
- **Feasible**: Only applied to small candidate set (10-100 docs)

## Types of Rerankers

### Cross-Encoder Models
- Joint encoding of query + document
- BERT-based: ms-marco-MiniLM, BGE-reranker
- Most accurate but slow
- ~10-100ms per query-doc pair

### Learned Rerankers
- Lightweight models trained on retrieval data
- Faster than cross-encoders
- Examples: Cohere rerank, Jina reranker

### Late Interaction
- ColBERT-style reranking
- Token-level interactions
- Balance of speed and accuracy

## Reranking Process

```
Query: "How do transformers work?"

1. Initial Retrieval (bi-encoder):
   - Retrieve top-100 candidates
   - Fast (~10ms)

2. Reranking (cross-encoder):
   - Score each of 100 candidates
   - Reorder by relevance
   - Return top-10
   - Slower (~1s for 100 docs)

3. Final Results:
   - Highest quality top-10 results
   - Much better than initial retrieval alone
```

## Performance Impact

Typical improvements:
- 10-30% better NDCG@10
- 15-40% better MRR (Mean Reciprocal Rank)
- Especially valuable for RAG quality

## Popular Reranker Models

### Open Source
- **BGE-reranker-large**: High quality, BAAI
- **ms-marco-MiniLM-L-12-v2**: Fast, Microsoft
- **Jina reranker-v2**: Multilingual support

### Commercial APIs
- **Cohere Rerank**: State-of-the-art, multilingual
- **Voyage AI Rerank**: High performance
- **OpenAI** (via fine-tuned models)

## Use Cases

- **RAG Systems**: Improve context quality for LLMs
- **Search Engines**: Better result ordering
- **Question Answering**: Find most relevant passages
- **Recommendation**: Refine initial candidates
- **Enterprise Search**: Precision-critical applications

## Implementation Example

```python
# 1. Initial retrieval
candidates = vector_db.search(query_embedding, top_k=100)

# 2. Reranking
reranked = reranker.rank(
    query=query,
    documents=[c.text for c in candidates],
    top_k=10
)

# 3. Use top results
context = reranked[:5]
```

## Trade-offs

### Advantages
- Significantly better accuracy
- More nuanced relevance
- Handles complex queries better
- Improves RAG quality

### Disadvantages
- Added latency
- Additional computational cost
- More complex pipeline
- Requires separate model/API

## Best Practices

- Retrieve more candidates initially (50-200)
- Rerank to smaller final set (5-20)
- Use async/parallel processing
- Cache reranking results when possible
- Monitor latency budget
- A/B test impact on quality

## Integration

Supported by:
- LangChain (Cohere, custom)
- LlamaIndex (multiple rerankers)
- Haystack (reranking nodes)
- Direct API calls (Cohere, Voyage)

## Pricing

Varies by reranker API or self-hosted compute costs.