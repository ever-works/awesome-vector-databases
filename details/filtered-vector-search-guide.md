## Overview

Filtered vector search combines semantic similarity with metadata constraints. The choice between pre-filtering and post-filtering significantly impacts performance, accuracy, and completeness of results.

## Pre-Filtering (Filter-Then-Search)

Metadata is used as the primary filter before vector search takes place, meaning only data meeting metadata criteria is passed into the vector search process.

### Advantages
- Can guarantee k results if users need k most similar documents
- Can yield more accurate results
- Dramatically improves both relevance and performance for selective queries

### Challenges
- HNSW algorithm experiences significant drop in search effectiveness when filtering ratio is low
- For highly selective filters, significant portion of graph must be traversed
- Increases computation cost and latency while reducing throughput

## Post-Filtering (Search-Then-Filter)

Applies filters after query execution, narrowing search results and processing results within each shard before merging.

### Advantages
- More accessible to implement
- Latency and throughput are more predictable
- Traversal cost isn't correlated with filter selectivity

### Disadvantages
- Can lead to incomplete results
- For highly selective filters, can reduce recall and produce false negatives
- Fewer matching documents returned than exist in index

## Hybrid & Modern Approaches (2026)

### Combined Strategies
Many systems combine both approaches, depending on the query:
1. Start with broad pre-filtering based on metadata
2. Apply more targeted vector search
3. Use post-filtering to refine results

### In-Algorithm Filtering

Modifies the index or search logic so ANN search itself only traverses or returns filtered vectors:

**Qdrant**: Adds extra graph links for filtered navigation
**Weaviate ACORN**: Performs two-hop expansions
**Pinecone**: Merges metadata and vector indexes into single index

### Pinecone Single-Stage Filtering (2026)

Produces accurate results of pre-filtering at even faster speeds than post-filtering by merging vector and metadata indexes. Combines accuracy benefits of pre-filtering with speed advantages of post-filtering.

## Best Practices

- Use pre-filtering for highly selective filters where result accuracy is critical
- Use post-filtering for less selective filters where speed is priority
- Consider hybrid approaches for production systems
- Monitor recall metrics when using post-filtering
- Benchmark both approaches with your actual query patterns

## The Missing WHERE Clause

Filtering has been called "The Achilles Heel of Vector Search" and "The Missing WHERE Clause." Modern solutions in 2026 focus on making filtered vector search as natural as SQL WHERE clauses while maintaining performance.