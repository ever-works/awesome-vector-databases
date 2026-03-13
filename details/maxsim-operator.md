## Overview

MaxSim (Maximum Similarity) is a scoring function used in late interaction retrieval models like ColBERT. It computes the relevance score between a query and document by finding the maximum similarity between each query token and all document tokens, then summing these maxima.

## How MaxSim Works

For each query token:
1. Compute similarity with all document tokens
2. Take the maximum similarity value
3. Sum these maximum values across all query tokens

## Key Characteristics

### Token-Level Matching

MaxSim enables fine-grained matching:
- Each query term finds its best match in the document
- Captures multi-aspect queries well
- Handles term importance naturally

### Computational Efficiency

While conceptually expensive, MaxSim can be optimized through pre-computed document embeddings and approximate nearest neighbor search.

## Use in ColBERT

ColBERT pioneered using MaxSim for dense retrieval, achieving state-of-the-art retrieval performance.

## Modern Applications

- ColBERT for text retrieval
- ColPali for visual document retrieval
- Jina ColBERT models
- Various late interaction models

## Trade-offs

**Advantages**:
- Higher accuracy than single-vector
- Better query understanding
- Interpretable results

**Disadvantages**:
- More storage (multiple vectors per document)
- More complex serving infrastructure

## Pricing

Implemented in open-source libraries (ColBERT, Vespa, etc.)