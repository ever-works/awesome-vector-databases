## Overview

Hybrid embeddings combine dense vectors (capturing semantics) with sparse vectors (capturing keywords) in a unified representation, providing best-of-both-worlds retrieval.

## Architecture

### Dense Component
- 384-1536 dimensions
- Semantic similarity
- Handles synonyms, paraphrasing
- Neural network generated

### Sparse Component  
- 10K-30K dimensions (vocabulary size)
- Keyword matching
- Exact term overlap
- SPLADE, BM25, or learned sparse

## Advantages

- **Better Recall**: Catches both semantic and lexical matches
- **Robustness**: Works across query types
- **Explainability**: Sparse component shows matched terms
- **Quality**: Best retrieval performance in benchmarks

## Implementation

```python
# Qdrant with named vectors
client.upsert(
    collection_name="hybrid_collection",
    points=[
        {
            "id": 1,
            "vector": {
                "dense": [0.1, 0.2, ...],  # 384 dims
                "sparse": {1: 0.5, 42: 0.3, ...}  # vocab indices
            },
            "payload": {"text": "..."}
        }
    ]
)

# Search both
results = client.search(
    collection_name="hybrid_collection",
    query_vector=("dense", query_dense),
    sparse_vector=("sparse", query_sparse),
    fusion="rrf"  # Reciprocal rank fusion
)
```

## Use Cases

- E-commerce search (product names + descriptions)
- Legal/medical (exact terms + concepts)
- Code search (identifiers + semantics)
- Any domain needing both precision and recall

## Pricing

Depends on vector database and embedding models used.