## Overview

Embedding dimensionality refers to the number of dimensions in a vector embedding, directly impacting storage, performance, and accuracy.

## Common Dimensions

### Small (384-512)

- **Examples**: MiniLM models
- **Pros**: Fast, low memory
- **Cons**: Less information capacity
- **Use**: Resource-constrained, high-throughput

### Medium (768-1024)

- **Examples**: BERT-base, many SBERT models
- **Pros**: Good balance
- **Cons**: Moderate resource needs
- **Use**: General purpose

### Large (1536-2048)

- **Examples**: text-embedding-3-large, BGE-large
- **Pros**: Rich representations
- **Cons**: Higher costs
- **Use**: Quality-critical applications

### Very Large (3072-4096)

- **Examples**: Gemini Embedding 2 (3072)
- **Pros**: Maximum capacity
- **Cons**: Significant resource requirements
- **Use**: Specialized, high-accuracy needs

## Matryoshka Embeddings

Variable-size embeddings:
- One model, multiple dimensions
- Truncate without retraining
- Example: Gemini Embedding 2 (3072/1536/768)

## Tradeoffs

### Higher Dimensions

**Advantages**:
- More information
- Better accuracy
- Richer semantics

**Disadvantages**:
- More storage
- Slower search
- Higher memory
- Increased costs

## Selection Criteria

- Task complexity
- Performance requirements
- Budget constraints
- Scale of deployment

## Pricing

Dimensionality itself is a model property, affecting infrastructure costs.