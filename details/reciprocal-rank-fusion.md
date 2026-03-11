## Overview

Reciprocal Rank Fusion (RRF) is a simple yet effective method for combining ranked lists from different retrieval systems. It's become the standard approach for fusing results in hybrid RAG systems.

## How RRF Works

RRF combines rankings by:
1. Taking ranked lists from multiple systems (e.g., BM25 and dense vectors)
2. Computing reciprocal rank score: 1/(k + rank)
3. Summing scores across systems for each item
4. Re-ranking by combined scores

Parameter k (typically 60) controls score smoothing.

## In Production RAG (2026)

Standard implementation pattern:
1. Run dense and BM25 queries in parallel
2. Fuse ranked lists via RRF
3. Create diverse, high-confidence candidate set
4. Apply cross-encoder or ColBERT re-ranking over fused top-k (typically k=50-200)

## Advantages

- **Simple**: No training required
- **Effective**: Performs well across domains
- **Robust**: Handles differences in score distributions
- **Fast**: Lightweight computation
- **Proven**: Wide industry adoption

## Use Cases

- Hybrid search systems
- RAG retrieval pipelines
- Combining keyword and semantic search
- Multi-modal retrieval
- Ensemble retrieval methods

## Alternative Methods

- Linear combination
- Weighted fusion
- Learning-to-rank approaches

RRF remains popular due to simplicity and effectiveness.

## Implementation

Supported in most RAG frameworks:
- LangChain
- LlamaIndex
- Haystack
- Custom implementations