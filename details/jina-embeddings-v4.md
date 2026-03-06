## Overview

jina-embeddings-v4 is a 3.8B parameter model that embeds text and images through a unified pathway, supporting both dense and late-interaction retrieval. Particularly strong on visually rich document retrieval, outperforming proprietary models from Google, OpenAI, and Voyage AI.

## Key Features

- **Multimodal**: Unified embedding for text and images
- **3.8B Parameters**: Built on Qwen2.5-VL-3B-Instruct foundation
- **Dense + Late Interaction**: Supports multiple retrieval modes
- **1,536 Dimensions**: Compatible with many vector databases
- **Open Weights**: Available on Hugging Face for self-hosting
- **API Access**: Managed API with multiple tiers

## Pricing

### Token-Based Pricing
- **Cost**: Approximately $0.02 per million tokens
- **Free Trial**: 10 million tokens for new users with auto-generated API key

### Rate Limits by Tier
- **Free**: 100 RPM, 100K TPM, 2 concurrent requests
- **Paid**: 500 RPM, 2M TPM, 50 concurrent requests
- **Premium**: 5,000 RPM, 50M TPM, 500 concurrent requests

### Image Token Calculation
- Each tile costs 10 tokens
- Tiles are 28x28 pixels
- Image processing cost varies with image size

### Pricing Model Update
New pricing model introduced May 6, 2025. Users with auto-recharge enabled before this date maintain old pricing. New pricing applies to new purchases or modifications.

## Important Note on Throughput

Jina intentionally throttles API throughput for jina-embeddings-v4 to manage infrastructure costs. For production workloads requiring high throughput:
- Use jina-embeddings-v3 API, or
- Deploy jina-embeddings-v4 on your own infrastructure via Hugging Face

## Payment Methods

Payments processed through Stripe supporting:
- Credit cards
- Google Pay
- PayPal

## Model Access

- **API**: https://jina.ai/embeddings/
- **Hugging Face**: jinaai/jina-embeddings-v4
- **Self-Hosting**: Deploy on your infrastructure
- **Cloud Marketplaces**: Azure Marketplace

## Use Cases

- Visually rich document retrieval
- Multimodal semantic search
- Document understanding with layout
- Cross-modal retrieval (text→image, image→text)
- RAG systems with visual content

## Comparison to v3

v4 adds multimodal capabilities (text + images) with 1,536-dimensional vectors, while v3 was text-only with 1,024 dimensions. v3 offers higher API throughput for production text-only workloads.