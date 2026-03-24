## Overview

Multi-Vector Embeddings represent documents or images as sequences of vectors rather than single vectors, enabling more nuanced semantic matching and better retrieval quality.

## Architecture

- Each token/patch gets its own vector
- Typical output: 128 dimensions per token
- Variable length based on content
- Stored and indexed together

## Comparison to Single-Vector

### Single-Vector (Dense)
- One vector per document
- Fixed dimensionality (e.g., 768 or 1536)
- Fast similarity computation
- Less storage

### Multi-Vector
- Multiple vectors per document
- Captures fine-grained semantics
- Better retrieval quality
- More storage needed

## Implementation Examples

### ColBERT
Pioneered multi-vector retrieval for text with MaxSim aggregation.

### Jina Embeddings v4
Supports both single-vector (2048-dim) and multi-vector (128-dim per token) embeddings.

## Retrieval Process

1. Encode query into multiple vectors
2. Encode documents into multiple vectors
3. Compute token-level similarities
4. Aggregate (typically MaxSim)
5. Rank documents

## Trade-offs

- **Quality**: Significantly better than single-vector
- **Storage**: 5-20x more space
- **Speed**: Slower similarity computation
- **Scalability**: Requires specialized indexing

## Pricing

Implementation approach, supported by various tools.