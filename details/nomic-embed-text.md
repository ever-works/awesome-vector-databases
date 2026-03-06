## Overview

Nomic-embed-text is the first fully reproducible, open-source text embedding model with 8,192 context length that outperforms both OpenAI Ada-002 and text-embedding-3-small on short and long context benchmarks.

## Key Features

- **Fully Open Source**: Training code, model weights, and complete training data released
- **Apache 2.0 License**: Free for commercial use
- **8,192 Context Length**: Long context support
- **Reproducible**: Complete replication possible with released data and code
- **High Performance**: Outperforms OpenAI models on MTEB benchmarks

## Model Versions

### V1 (nomic-embed-text-v1)
- First fully reproducible embedding model
- 8,192 context length
- Trained on weakly related text pairs and high-quality labeled datasets
- English-focused

### V1.5 (nomic-embed-text-v1.5)
- Matryoshka Representation Learning support
- Flexible embedding dimensions
- Trade-off between size and performance
- Minimal performance reduction with smaller dimensions

### V2 (nomic-embed-text-v2)
- **Mixture-of-Experts (MoE) Architecture**: First MoE text embedding model
- **Multilingual**: Trained on 1.6 billion contrastive pairs across ~100 languages
- **Expanded Dataset**: Broader multilingual coverage
- **Production-Ready**: Optimized for real-world applications

## Training Approach

1. **Stage 1 - Unsupervised Contrastive**: Training on weakly related text pairs from StackExchange, Quora, Amazon reviews, news articles
2. **Stage 2 - Fine-tuning**: Leverages high-quality labeled datasets including search queries and web search answers

## Access Methods

- **Hugging Face**: Direct model download and inference
- **Ollama**: `ollama pull nomic-embed-text`
- **Nomic API**: Managed API endpoint
- **LlamaIndex Integration**: Native support
- **Qdrant Integration**: Built-in connector

## Use Cases

- Long-context semantic search
- Multilingual retrieval applications
- Document embedding and clustering
- RAG systems requiring long context
- Research requiring reproducibility

## Performance Highlights

- Outperforms OpenAI text-embedding-ada-002
- Competitive with text-embedding-3-small
- Strong performance on both short and long context tasks
- Excellent multilingual capabilities (v2)

## Pricing

Free and open-source under Apache 2.0 license. No licensing costs. Nomic API offers managed hosting with usage-based pricing for convenience.