## Overview

Reciprocal Rank Fusion (RRF) is an algorithm that evaluates search scores from multiple, previously ranked results to produce a unified result set, merging and homogenizing the rankings into a single result set for the query response.

## Key Advantages

### Normalization-Free
You don't need to know the distribution of your vector or BM25 scores as RRF works purely on position, avoiding score distribution issues by focusing exclusively on rank positions.

### Outlier Resistance
Because RRF aggregates rankings rather than scores, it prevents anomalous values from distorting relevance.

### Scalability
Extremely efficient for sharded, billion-scale indices where global score normalization is expensive.

## How It Works

For each document in search results, the engine assigns a reciprocal rank score based on its position:

**Formula**: score = 1/(rank + k)

Where:
- rank = position of the document
- k = constant (experiments show best results with k=60)

## 2026 Implementations

### OpenSearch 2.19
Introduces RRF as a new feature in the Neural Search plugin that enhances hybrid search by merging ranked results from multiple query sources (neural search, k-NN, Boolean queries).

### Azure AI Search
RRF is used when two or more queries execute in parallel, for hybrid queries and multiple vector queries.

### Google Cloud Vertex AI
Uses RRF to merge token-based and semantic search results.

## Common Use Cases

RRF is an excellent "first stage" reranker. Common pattern:
1. Retrieve top 100 documents via RRF
2. Use more expensive Cross-Encoder to rank top 10 for LLM context window

## Best Practices

RRF is the best starting point for hybrid search because of its simplicity and resilience to mismatched score scales.