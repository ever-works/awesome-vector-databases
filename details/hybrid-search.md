## Overview

Hybrid Search combines dense vector embeddings (semantic search) with sparse representations like BM25 or SPLADE (lexical search) into a single unified search system. This approach provides the best overall search quality by leveraging the complementary strengths of both methods.

## How It Works

Hybrid search executes two parallel searches:
1. **Dense Vector Search**: Semantic similarity using embeddings
2. **Sparse/Lexical Search**: Keyword matching using BM25, TF-IDF, or SPLADE
3. **Fusion**: Combines results using reciprocal rank fusion or weighted scoring

## Why Hybrid Search?

**Dense search is good at**:
- Understanding semantic meaning and context
- Handling synonyms and paraphrasing
- Cross-lingual retrieval
- Conceptual similarity

**Sparse search is good at**:
- Exact keyword matching
- Proper nouns and technical terms
- Acronyms and abbreviations
- Out-of-vocabulary terms

## Fusion Techniques

### Reciprocal Rank Fusion (RRF)
Combines rankings from both methods:
```
score(d) = Σ 1/(k + rank_i(d))
```
where k is typically 60

### Weighted Linear Combination
Combines scores with weights:
```
score = α × dense_score + (1-α) × sparse_score
```

## Implementation Patterns

1. **Parallel Execution**: Run both searches concurrently
2. **Result Merging**: Combine and deduplicate results
3. **Reranking**: Optional final reranking with cross-encoder

## Industry Adoption (2026)

Hybrid search is now the industry standard for production RAG systems, with major platforms supporting it natively:
- Azure AI Search
- Google Vertex AI Vector Search
- Elasticsearch
- Qdrant
- Weaviate

## Best Practices

- Start with equal weighting (0.5/0.5) and tune based on eval
- Use reciprocal rank fusion for simplicity
- Consider domain-specific weighting
- Monitor both dense and sparse components separately
- Implement proper evaluation metrics

## Performance Characteristics

- Slightly slower than pure vector search (2 searches + fusion)
- Significantly better recall and precision
- More robust to edge cases
- Better handling of diverse query types

## Example Results

Typical improvements over vector-only search:
- 10-20% better recall
- 15-25% better NDCG
- More consistent performance across query types

## Use Cases

- Enterprise search over diverse content
- E-commerce product search
- Legal and medical document retrieval
- Code search
- Customer support knowledge bases

## Pricing

Implementation-dependent; some vector databases include hybrid search at no additional cost.