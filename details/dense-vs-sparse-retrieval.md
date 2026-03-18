## Dense Retrieval

**What**: Neural embeddings in continuous vector space

**Strengths**:
- Semantic understanding
- Handles synonyms and paraphrasing
- Good for conceptual queries
- Captures context
- Language model powered

**Weaknesses**:
- May miss exact matches
- Struggles with rare terms
- Black box (not interpretable)
- Requires neural models
- Higher computational cost

**Best For**:
- Semantic search
- Question answering
- Similar document finding
- Cross-lingual search

## Sparse Retrieval

**What**: Traditional keyword-based methods (TF-IDF, BM25)

**Strengths**:
- Exact matching
- Fast and efficient
- Interpretable
- Good with rare terms
- No training needed
- Low computational cost

**Weaknesses**:
- No semantic understanding
- Vocabulary mismatch problem
- Requires exact terms
- Poor with synonyms
- Limited context

**Best For**:
- Keyword search
- Entity/name matching
- Technical term search
- ID/code lookup
- Legal/compliance queries

## Side-by-Side Comparison

| Aspect | Dense | Sparse |
|--------|-------|--------|
| Semantic | ✓✓ | ✗ |
| Exact Match | ✗ | ✓✓ |
| Speed | Medium | Fast |
| Interpretable | ✗ | ✓✓ |
| Setup Cost | High | Low |
| Storage | Medium | Low |
| Out-of-domain | Good | Poor |

## When Dense Fails

- Searching for specific IDs
- Rare technical terms
- Proper nouns (people, places)
- Acronyms
- Exact phrase matching
- Out-of-vocabulary terms

## When Sparse Fails

- Synonym variations
- Paraphrased queries
- Conceptual search
- Cross-lingual queries
- Context-dependent meaning
- Implicit information needs

## Hybrid Approach (Best of Both)

**Combination Methods**:
1. **Parallel Retrieval**: Query both, merge results
2. **Sequential**: Sparse filter → Dense rerank
3. **Ensemble**: Weighted combination

**Result Fusion**:
- Reciprocal Rank Fusion (RRF)
- Linear combination
- Learned fusion weights

**Benefits**:
- 10-20% better than either alone
- Robust across query types
- Handles edge cases

**Implementation**:
```python
# Get results from both
sparse_results = bm25_search(query)
dense_results = vector_search(embed(query))

# Combine with RRF
final = reciprocal_rank_fusion(
    sparse_results,
    dense_results,
    k=60
)
```

## Learned Sparse Retrieval

**SPLADE, etc.**:
- Neural model learns sparse representations
- Combines benefits of both
- Interpretable + semantic
- Expanding vocabulary

## Database Support

**Dense Only**:
- Pinecone (primary)
- Chroma
- Voy

**Hybrid Native**:
- Elasticsearch
- OpenSearch
- Weaviate
- Qdrant
- Vespa

## Selection Guide

**Use Dense When**:
- Semantic understanding critical
- General knowledge queries
- User-written queries
- Cross-lingual needs

**Use Sparse When**:
- Exact matching required
- Technical/specialized terms
- IDs or codes
- Budget/speed constrained

**Use Hybrid When**:
- Production RAG systems
- Diverse query types
- Quality critical
- Can afford complexity

## Modern Trend

Industry moving toward hybrid as default for production RAG systems, with ~70% of production systems using some form of hybrid retrieval.