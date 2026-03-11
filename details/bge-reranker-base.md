## Overview

BGE Reranker Base is a cross-encoder model specifically designed for reranking retrieved documents in RAG pipelines. Unlike bi-encoders that create separate embeddings, it processes query-document pairs together for more accurate relevance scoring.

## Features

- **Cross-Encoder Architecture**: Processes query and document together
- **High Accuracy**: Near-highest MRR for embeddings
- **Open Source**: Apache 2.0 license for commercial use
- **Self-Hostable**: Run on your own infrastructure
- **Cost-Effective**: No API fees after deployment
- **GPU Optimized**: 50-100ms latency on GPU
- **Production Ready**: Used in many production systems

## Performance

Frequently offers the highest or near-highest MRR (Mean Reciprocal Rank) for embeddings, with performance rivaling or surpassing proprietary models like Cohere Rerank.

## Use Cases

- Improving RAG retrieval accuracy
- Re-ranking search results
- Question answering systems
- Document relevance scoring
- Information retrieval pipelines

## Integration

Works with LangChain, LlamaIndex, and Hugging Face Transformers. Can be deployed alongside vector databases for two-stage retrieval.

## Model Variants

- **bge-reranker-base**: Balanced performance and speed
- **bge-reranker-large**: Higher accuracy, more compute
- **bge-reranker-v2-m3**: Multilingual support for 100+ languages

## Pricing

Free and open-source under Apache 2.0 license. Hosting costs depend on deployment infrastructure.