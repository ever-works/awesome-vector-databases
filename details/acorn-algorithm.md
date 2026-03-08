## Overview

ACORN (Approximate k-Nearest Neighbors with HNSW Over Refined Neighborhoods) is an approach for performant and predicate-agnostic hybrid search that builds on HNSW and can be implemented efficiently by extending existing HNSW libraries.

## Two-Hop Neighborhood Strategy

The two-hop expansion is a key innovation in ACORN:
- Evaluates nodes that are two hops away rather than one
- Target nodes become out-neighbors of search nodes (two hops away)
- Speeds up graph traversal
- Ameliorates challenges of low correlation between filters and query vectors

## How It Works

ACORN builds on Hierarchical Navigable Small Worlds (HNSW), a state-of-the-art graph-based approximate nearest neighbor index. The algorithm uses a two-hop based expansion of the neighborhood to maintain search quality when filters are applied.

## Weaviate Implementation (2026)

Weaviate uses ACORN to keep recall high under selective filters:

### Conditional Two-Hop Evaluation
- If the first hop passes the filter, traverse graph normally
- Only use two-hop expansion if connecting node doesn't pass filter
- Optimizes performance based on filter selectivity

### Benefits in Production
- Combines semantic similarity with structured filters
- Keeps filtered queries efficient on realistic datasets
- Designed specifically for vector search with rich filtering over high-dimensional spaces

## Performance Characteristics

- Maintains high recall even with selective filters
- Efficient implementation by extending HNSW libraries
- Predicate-agnostic: works well regardless of filter characteristics

## Research Impact

Published in Proceedings of the ACM on Management of Data (2024), ACORN represents a significant advancement in filtered vector search, addressing one of the main challenges in production vector database deployments.

## Applications

- E-commerce search with category/price filters
- Document retrieval with metadata constraints
- Multi-tenant vector databases
- Any scenario requiring hybrid semantic + structured search