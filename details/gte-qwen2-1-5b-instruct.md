## Overview

gte-Qwen2-1.5B-instruct is the latest model in the GTE (General Text Embedding) model family from Alibaba, built on the Qwen2-1.5B LLM architecture. The model uses the same training data and strategies as the larger gte-Qwen2-7B-instruct model while maintaining a more compact size.

## Key Features

- **Bidirectional Attention**: Integration of bidirectional attention mechanisms enriches contextual understanding
- **Multilingual Support**: Comprehensive training across a vast, multilingual text corpus spanning diverse domains and scenarios
- **Long Context**: Maximum sequence length of 8192 tokens
- **Advanced Training**: Leverages both weakly supervised and supervised data for robust performance

## Model Performance

The larger gte-Qwen2-7B-instruct model achieved a score of 70.24 on the MTEB benchmark, outperforming:
- NV-Embed-v1 (69.32)
- gte-Qwen1.5-7B-instruct (67.34)

## Availability

The GTE series models are available:
- On Hugging Face for open-source use
- As commercial API services on Alibaba Cloud (text-embedding-v1/v2/v3)
- Compatible with Sentence Transformers framework

## Use Cases

- Multilingual semantic search
- Cross-lingual information retrieval
- RAG (Retrieval-Augmented Generation) applications
- Document clustering and classification
- Embedding generation for vector databases

## Model Variants

The GTE-Qwen2 series includes:
- gte-Qwen2-1.5B-instruct (1.5 billion parameters)
- gte-Qwen2-7B-instruct (7 billion parameters)

## Technical Details

Developed by Tongyi Lab of Alibaba Group, last updated January 21, 2025. The model represents the state-of-the-art in multilingual embedding models for 2026.