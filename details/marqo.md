## Overview

Marqo is a vector search engine and database designed for multimodal data, supporting ingestion and querying of text, images, and videos via a unified API.

## Features

- Multimodal storage for text, image, and video vectors
- Cross-modal search (e.g., text-to-image, image-to-text)
- CLIP embedding support alongside Hugging Face models for auto-vectorization
- Managed cloud and self-hosted deployment options
- Unified API for multi-model search

## Use Cases

- Visual RAG: Retrieve relevant images/videos to augment LLM prompts
- Multimedia retrieval: Search large collections of mixed media content
- E-commerce product discovery with image and text queries

## Comparison vs Text-Only Qdrant

| Feature | Marqo | Qdrant |
|---------|--------|--------|
| Modalities | Text, image, video | Primarily text vectors |
| Cross-Modal Search | Native support | Limited, requires external handling |
| Auto-Vectorization | Built-in via HF models | Manual embedding required |
| Deployment | Cloud/self-hosted | Self-hosted primarily |

## Pricing

Contact Marqo for enterprise pricing details. Offers developer free tier for prototyping.

## Integrations

- LangChain, LlamaIndex
- Shopify, Adobe Commerce