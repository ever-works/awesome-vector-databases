## Overview

Query expansion improves retrieval by generating multiple variations of user queries or adding related terms, increasing the chance of finding relevant documents.

## Techniques

**HyDE (Hypothetical Document Embeddings)**:
- Generate hypothetical answer to query
- Embed the answer instead of query
- Documents similar to answers, not questions
- 5-15% improvement in retrieval

**Multi-Query**:
- Generate 3-5 query variations
- Search with each variation
- Combine results (union or intersection)
- Captures different phrasings

**Query Rewriting**:
- Use LLM to reformulate query
- Clarify ambiguous terms
- Add context
- Improve searchability

**Term Expansion**:
- Add synonyms
- Include related concepts
- Expand acronyms
- Traditional IR technique

**Sub-Query Decomposition**:
- Break complex queries into parts
- Search each independently
- Combine results
- Better for multi-faceted questions

## Implementation Examples

**HyDE**:
```python
# Generate hypothetical answer
hypothetical = llm.generate(f"Answer this question: {query}")
# Embed and search
emb = embed(hypothetical)
results = vector_db.search(emb)
```

**Multi-Query**:
```python
variations = llm.generate(f"Generate 3 variations: {query}")
all_results = []
for var in variations:
    results = vector_db.search(embed(var))
    all_results.extend(results)
# Deduplicate and rerank
```

## When to Use

**HyDE**: Complex questions, technical domains
**Multi-Query**: Ambiguous queries, broad topics
**Query Rewriting**: User queries need clarification
**Sub-Query**: Complex multi-part questions

## Trade-offs

**Benefits**:
- Better recall
- More robust to query phrasing
- Improved user experience

**Costs**:
- Additional LLM calls
- Higher latency
- More vector searches
- Increased complexity

## Best Practices

1. Test impact on your data
2. Monitor latency increase
3. Cache generated variations
4. Combine with reranking
5. A/B test effectiveness
6. Balance recall vs precision