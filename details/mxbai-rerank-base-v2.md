## Overview

mxbai-rerank-base-v2 is a second-generation reranking model from Mixedbread AI that combines compact size with state-of-the-art performance. It is fully open-source under the Apache 2.0 license.

## Key Features

- **Reinforcement Learning**: Trained using GRPO (Guided Reinforcement Prompt Optimization) for enhanced performance
- **Multilingual**: Supports 100+ languages for global applications
- **Extended Context**: Handles up to 8K tokens (32K-compatible) for comprehensive document analysis
- **Fast Processing**: Up to 8x faster than comparable solutions
- **Compact Size**: 0.5B parameters provide optimal balance of size and performance

## Performance

Benchmark results on standard datasets:
- **BEIR Average**: 55.57 NDCG@10
- **Mr.TyDi (Multilingual)**: 28.56 NDCG@10
- **Chinese Datasets**: 83.70 NDCG@10
- **Code Search**: 31.73 NDCG@10

## Integration

The rerank model can be added to the end of an existing keyword-based search workflow (Elasticsearch, OpenSearch, Solr), allowing semantic relevance to be incorporated without changing existing infrastructure.

## Use Cases

- Improving search relevance in RAG applications
- Re-ranking results from BM25 or vector search
- Multi-stage retrieval pipelines
- Code search and technical documentation
- Multilingual search applications

## Pricing

Free and open-source under Apache 2.0 license. Also available via Mixedbread API with usage-based pricing.