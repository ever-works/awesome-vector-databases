## Overview

Binary quantization compresses high-dimensional vectors by representing each component as a single bit, either 0 or 1. This method can achieve up to a 40x retrieval speed gain and results in up to 28 times reduced vector index size.

## How It Works

The technique marks all numbers greater than zero as 1, and those zero or less become 0. Binary quantization performs very well when embeddings are centered around zero.

## Performance Characteristics

- **Speed**: Up to 40x faster retrieval
- **Compression**: Up to 28x reduced vector index size
- **Accuracy**: Best for embeddings centered around zero

## Compatibility

Works particularly well with popular embedding models offered by:
- OpenAI
- Cohere
- Mistral

These models produce embeddings centered around zero, making them ideal candidates for binary quantization.

## Recent Developments (2025-2026)

Starting from Qdrant v1.15.0, two additional quantization types were introduced:
- **1.5-bit binary quantization**: Useful middle ground between scalar and standard binary
- **2-bit binary quantization**: Provides more precision than 1-bit while maintaining high compression

## Trade-offs

### Rescoring
Rescoring is an optional technique used to offset information loss due to vector quantization. It uses oversampling to pick up extra vectors and supplemental information to rescore initial results.

### Best Use Cases
- Large-scale retrieval systems
- Memory-constrained environments
- Applications prioritizing speed over perfect accuracy
- Embeddings naturally centered around zero

## Comparison with Scalar Quantization

Binary quantization offers more aggressive compression (32x) compared to scalar quantization (4x), but scalar quantization maintains higher accuracy for embeddings not centered around zero.