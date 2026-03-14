## Overview

Hybrid search combines keyword search (BM25) and semantic search (vector similarity) to get the benefits of both: the precision of lexical matching and the semantic understanding of neural models.

## The Fusion Challenge

Different search methods produce scores on incompatible scales:
- **BM25 scores**: Unbounded, influenced by term frequency and distribution
- **Vector similarity scores**: Fixed range (e.g., 0-1 for cosine similarity)

This incompatibility makes direct score combination problematic.

## Reciprocal Rank Fusion (RRF)

RRF offers an elegant solution that sidesteps score normalization by focusing solely on the rank of each document within individual result lists.

### RRF Formula

```
RRF_score = Σ 1 / (rank + k)
```

Where:
- **rank**: Position of document in the result list
- **k**: Constant (typically 60 based on research)

### How RRF Works

1. Run BM25 keyword search → get ranked list A
2. Run vector semantic search → get ranked list B
3. For each document:
   - Calculate 1/(rankA + k) + 1/(rankB + k)
4. Sort by combined RRF score

## Key Advantages

- **No normalization needed**: Avoids complex score scaling
- **Position-based**: Values documents ranked highly in multiple lists
- **Robust**: Works well across different search methods
- **Simple**: Easy to implement and understand
- **Effective**: Often outperforms individual methods

## Hybrid Search Benefits

### Lexical Search (BM25) Strengths:
- Exact keyword matching
- Technical terms and names
- Specific identifiers (SKUs, codes)
- Boolean logic

### Semantic Search (Vector) Strengths:
- Conceptual similarity
- Synonyms and paraphrases
- Context understanding
- Cross-lingual search

### Combined (Hybrid):
- Best of both worlds
- Handles diverse query types
- Improved relevance
- Better recall and precision

## Implementation Examples

### Elasticsearch
```json
{
  "query": {
    "hybrid": {
      "queries": [
        { "match": { "content": "search query" } },
        { "knn": { "field": "embedding", "vector": [...] } }
      ],
      "rank": { "rrf": { "window_size": 100, "rank_constant": 60 } }
    }
  }
}
```

### Performance Impact

Studies show hybrid search with RRF can improve:
- Retrieval accuracy: 10-30% over single method
- Answer quality: 15-25% in RAG systems
- User satisfaction: Significantly better relevance

## Alternative Fusion Methods

- **Linear combination**: Weighted sum of normalized scores
- **Convex combination**: Weighted average with α parameter
- **CombSUM/CombMNZ**: Score-based fusion strategies

**RRF is preferred** for its simplicity and robustness.

## Platform Support

- Elasticsearch (native RRF)
- OpenSearch (Neural Search plugin)
- Weaviate
- Azure AI Search
- PostgreSQL (ParadeDB + pgvector)
- Qdrant
- Pinecone

## Best Practices

1. **Set k=60**: Research-backed optimal value
2. **Balance weights**: Consider query type for weighting methods vs keywords
3. **Test both approaches**: Compare RRF vs weighted combinations
4. **Monitor metrics**: Track relevance improvements
5. **Use reranking**: Add cross-encoder for final refinement

## Use Cases

- E-commerce search (products + descriptions)
- Enterprise search (documents + technical content)
- Question answering (exact facts + contextual answers)
- Legal/medical search (precise terms + conceptual similarity)

## Pricing

Implementation technique, included in vector database platforms at no additional cost.