## Overview

Matryoshka Representation Learning (MRL) is a training technique that enables models to produce embeddings where truncated versions maintain good performance. Named after Russian nesting dolls, it allows you to use different embedding sizes from the same model without retraining.

## How It Works

During training, the model learns to encode information at multiple granularities:
- Important information in early dimensions
- Progressively more detailed information in later dimensions
- Each prefix (e.g., first 128, 256, 512 dims) forms a valid embedding

## Key Benefits

### Cost Savings

75% cost savings when storing 768-dimensional versus 3,072-dimensional vectors:
- Less storage required
- Faster similarity search
- Lower infrastructure costs

### Flexibility

One model, multiple use cases:
- Use 128-dim for initial filtering
- Use 512-dim for production search
- Use 1024-dim for highest accuracy scenarios

### No Retraining

Truncate vectors to smaller dimensions without retraining the model, unlike traditional dimensionality reduction techniques.

## Performance Characteristics

- Minimal accuracy loss when truncating to reasonable sizes
- Better than PCA or other post-hoc dimension reduction
- Enables dynamic precision-recall trade-offs

## Modern Adoption

Most modern embedding models in 2026 support Matryoshka Representation Learning:
- Nomic Embed
- Mixedbread AI models
- Cohere Embed v4
- Voyage AI models
- Many Hugging Face models

## Use Cases

- Multi-stage retrieval pipelines
- Resource-constrained deployments
- Trading accuracy for speed/cost
- Progressive refinement search

## Implementation

Simply truncate the embedding vector to desired dimension.

## Pricing

Available in many open-source and commercial embedding models.