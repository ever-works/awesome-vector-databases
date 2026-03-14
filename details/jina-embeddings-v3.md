## Overview

jina-embeddings-v3 is a frontier multilingual text embedding model with 570M parameters and 8192 token-length, outperforming the latest proprietary embeddings from OpenAI and Cohere on MTEB.

## Key Features

- **570M Parameters**: Balanced size for performance and efficiency
- **Long Context**: Supports up to 8192 tokens
- **Task-Specific LoRA Adapters**: Includes adapters for query-document retrieval, clustering, classification, and text matching
- **Matryoshka Embeddings**: Flexible dimension truncation (32, 64, 128, 256, 512, 768, 1024) without significant performance loss
- **Multilingual**: Supports 89 languages with strong multilingual performance

## Performance

- Outperforms OpenAI and Cohere embeddings on English tasks
- Superior performance compared to multilingual-e5-large-instruct across all multilingual tasks
- Better results than e5-mistral-7b-instruct, which has 12x more parameters

## Technical Details

- Default output dimension: 1024
- Supports dimension reduction to 32-768 with Matryoshka approach
- Available on Hugging Face: jinaai/jina-embeddings-v3
- Integration with Elastic Inference Service

## Use Cases

- Semantic search
- Document retrieval
- Clustering
- Classification
- Text matching
- Cross-lingual search

## Availability

- Hugging Face Hub
- Jina AI API
- Elastic Inference Service
- LlamaIndex integration

## Pricing

Available through Jina AI's API with both free tier and commercial plans.