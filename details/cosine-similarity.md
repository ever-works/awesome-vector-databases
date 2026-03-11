## Overview

Cosine similarity is the most widely used similarity metric in vector databases, measuring the cosine of the angle between two vectors in multi-dimensional space.

## Formula

Cosine similarity = (A · B) / (||A|| × ||B||)

Where:
- A · B is the dot product
- ||A|| and ||B|| are vector magnitudes

## Range and Interpretation

- **1**: Vectors point in same direction (identical)
- **0**: Vectors are orthogonal (unrelated)
- **-1**: Vectors point in opposite directions

## Advantages

- **Magnitude Independent**: Focuses on direction, not length
- **Normalized**: Values always between -1 and 1
- **Efficient**: Fast computation
- **Intuitive**: Easy to interpret

## Use Cases

- Text embedding similarity
- Document retrieval
- Recommendation systems
- Image similarity
- Semantic search

## Common in Vector Databases

- Pinecone: Default metric
- Weaviate: Supported metric
- Milvus: IP (inner product) variant
- Qdrant: Native support
- pgvector: Built-in operator

## Pricing

Algorithm, no licensing costs.