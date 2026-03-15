## Overview

L2 Normalization, also called vector normalization, is a preprocessing technique that scales vectors to unit length (magnitude = 1). This ensures all vectors lie on the surface of a unit hypersphere, which has important mathematical and computational benefits.

## Mathematical Definition

For a vector v, the L2-normalized vector v̂ is:

v̂ = v / ||v||₂

where ||v||₂ = sqrt(Σ vᵢ²) is the L2 norm (Euclidean length)

## Why Normalize?

- **Cosine = Inner Product**: Makes cosine similarity computationally equivalent to inner product
- **Scale Invariance**: Removes magnitude differences, focusing on direction
- **Stable Training**: Improves neural network training stability
- **Consistent Comparison**: Ensures fair comparison between embeddings
- **Performance**: Faster similarity search (inner product is faster than cosine)

## Common Applications

- **Embedding Models**: Most modern embedding models output normalized vectors
- **Face Recognition**: Normalize face embeddings for similarity comparison
- **Sentence Embeddings**: Standard practice in NLP models
- **Image Embeddings**: Common in computer vision applications
- **Recommendation Systems**: Normalize user and item vectors

## Implementation

```python
import numpy as np

def l2_normalize(vector):
    norm = np.linalg.norm(vector)
    if norm == 0:
        return vector
    return vector / norm
```

## When to Normalize

**Before Indexing**: Normalize vectors before adding to vector database
**Before Querying**: Normalize query vectors to match indexed vectors
**During Training**: Some models normalize internally

## Impact on Distance Metrics

With normalized vectors:
- Inner Product = Cosine Similarity
- Euclidean Distance relates to Cosine Distance
- Angular distance becomes meaningful

## Popular Models Using Normalization

- Sentence-BERT (SBERT)
- CLIP
- OpenAI text-embedding models
- Cohere embeddings
- Many face recognition models

## Best Practices

1. Check if your embedding model already normalizes outputs
2. Normalize consistently (both index and query vectors)
3. Be aware of zero vectors (handle division by zero)
4. Document normalization status in production systems

## Performance Benefits

- 2-3x faster similarity computation (inner product vs. cosine)
- Enables more efficient indexing algorithms
- Simplifies distance calculations

## Pricing

Not applicable (mathematical preprocessing technique).