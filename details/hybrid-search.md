## Overview

Hybrid search combines traditional keyword search (BM25) with semantic vector search, leveraging strengths of both approaches.

## Components

### Keyword Search (BM25)
- Exact term matching
- Fast and efficient
- Handles specific terms well
- No semantic understanding

### Vector Search
- Semantic understanding
- Handles paraphrases
- Context-aware
- May miss specific terms

### Fusion (RRF)
- Combines result sets
- Balances both approaches
- Improves overall quality

## Advantages

- **Better Recall**: Catches more relevant results
- **Improved Precision**: Reduces irrelevant matches
- **Robust**: Works across query types
- **Best of Both**: Keyword precision + semantic understanding

## Implementation

1. Run parallel searches (BM25 + vector)
2. Get top-k from each
3. Apply fusion (RRF recommended)
4. Optional: Rerank fused results
5. Return final ranking

## Supported By

- Weaviate
- Qdrant
- Elasticsearch
- OpenSearch
- Milvus (via plugins)
- Vespa

## When to Use

- Production RAG systems
- Enterprise search
- When both precision and recall matter
- Diverse query types

## Pricing

Technique, costs from vector DB + compute.