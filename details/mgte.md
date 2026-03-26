## Overview

Alibaba's Tongyi Lab has introduced the GTE-Multilingual (mGTE) series which offers high performance, long-context handling, multilingual support, and elastic embedding, significantly improving retrieval and ranking efficiency.

## Key Features

The mGTE series includes new generalized text encoder, embedding and reranking models that support 75 languages and the context length of up to 8192 tokens.

## Architecture

### Transformer++ Encoder Backbone
The models are built upon the transformer++ encoder backbone (BERT + RoPE + GLU) as well as the vocabulary of XLM-R.

### Key Improvements
- **Rotary Position Encoding (RoPE)**: Replaces BERT's absolute position embeddings to better support long-context training
- **Gated Linear Units (GLU)**: Replaces the original feed-forward network (FFN) in BERT

## Model Specifications

- **Base model size**: 305M parameters
- **Embedding dimension**: 768
- **Max input tokens**: 8192
- **Language support**: 75 languages

## Performance

The text encoder outperforms the same-sized previous state-of-the-art XLM-R, while the embedding and reranker match the performance of large-sized state-of-the-art BGE-M3 models and achieve better results on long-context retrieval benchmarks.

## Model Variants

- **gte-multilingual-base**: For embeddings
- **gte-multilingual-reranker-base**: For reranking tasks
- **gte-multilingual-mlm-base**: Masked language model variant

## Availability

The models are available on:
- Hugging Face under the Alibaba-NLP organization
- Alibaba Cloud as commercial API services (text-embedding-v1/v2/v3)

## Use Cases

- Multilingual RAG applications
- Long-context retrieval
- Cross-lingual search
- Enterprise multilingual search
- Question answering across languages

## Integration

Supports integration with Milvus, LangChain, and other popular vector database and LLM frameworks.

## Pricing

Available as open-source models on Hugging Face or through Alibaba Cloud APIs with commercial pricing.