## Overview

Vector normalization transforms vectors to a standard scale, most commonly to unit length (magnitude = 1). This preprocessing step is fundamental to many vector search operations and embedding models.

## L2 Normalization

Most common type: scale to unit length

### Formula
```
normalized_vector = vector / ||vector||_2
where ||vector||_2 = √(Σ x_i²)
```

### Properties
- Resulting vector has length 1
- Direction preserved
- All vectors on unit hypersphere

### Example
```python
import numpy as np

vector = np.array([3, 4])
norm = np.linalg.norm(vector)  # 5.0
normalized = vector / norm     # [0.6, 0.8]
```

## Why Normalize?

### Cosine Similarity via Dot Product
For normalized vectors:
```
cosine_similarity(a, b) = dot_product(normalized_a, normalized_b)
```
No need for division by magnitudes!

### Faster Computation
- Pre-normalize vectors once
- Similarity = simple dot product
- Huge speedup for billion-scale search

### Scale Independence
- Removes magnitude information
- Focuses on direction/orientation
- Useful for text embeddings (document length irrelevant)

### Numerical Stability
- Prevents overflow/underflow
- More stable computations
- Better for training

## Common Normalization Types

### L2 Normalization (Unit Length)
**Use:** Cosine similarity, most embedding models
```python
vector / np.linalg.norm(vector)
```

### L1 Normalization
**Use:** Probability distributions, sparse vectors
```python
vector / np.sum(np.abs(vector))
```

### Min-Max Normalization
**Use:** Feature scaling
```python
(vector - vector.min()) / (vector.max() - vector.min())
```

### Z-Score Normalization
**Use:** Statistical analysis
```python
(vector - vector.mean()) / vector.std()
```

## In Vector Databases

### Automatic Normalization
Many databases normalize automatically:
- **Pinecone**: Normalizes for cosine similarity
- **Weaviate**: Optional normalization
- **Qdrant**: Depends on distance metric
- **Milvus**: Configurable

### Manual Control
Some require explicit normalization:
- **FAISS**: User responsible
- **Annoy**: User choice
- **pgvector**: User normalizes

## Embedding Models

### Pre-Normalized
Many models output normalized vectors:
- OpenAI embeddings (normalized)
- Cohere embed-v3 (normalized)
- Sentence Transformers (usually normalized)

### Unnormalized
Some models don't normalize:
- Check model documentation
- Normalize before storage
- Ensure consistency

## Implementation

### NumPy
```python
def l2_normalize(vectors):
    norms = np.linalg.norm(vectors, axis=1, keepdims=True)
    return vectors / norms
```

### PyTorch
```python
import torch.nn.functional as F
normalized = F.normalize(vectors, p=2, dim=1)
```

### TensorFlow
```python
import tensorflow as tf
normalized = tf.nn.l2_normalize(vectors, axis=1)
```

## Verification

### Check if Normalized
```python
norm = np.linalg.norm(vector)
print(f"Norm: {norm}")
print(f"Is normalized: {np.isclose(norm, 1.0)}")
```

### Batch Verification
```python
norms = np.linalg.norm(vectors, axis=1)
print(f"All normalized: {np.allclose(norms, 1.0)}")
```

## Common Mistakes

### Normalizing Twice
- Check if model already normalizes
- Can cause numerical issues
- Wastes computation

### Wrong Axis
- Normalize per vector, not per dimension
- `axis=1` for row vectors
- `axis=0` for column vectors

### Zero Vectors
- Division by zero error
- Handle edge case:
```python
def safe_normalize(vector):
    norm = np.linalg.norm(vector)
    if norm == 0:
        return vector
    return vector / norm
```

## Distance Metrics

### Affected by Normalization
- **Cosine Similarity**: Becomes dot product
- **Angular Distance**: Simplified
- **Euclidean Distance**: Changes meaning

### Unaffected
- **Manhattan Distance**: Still valid
- **Hamming Distance**: For binary vectors

## Best Practices

1. **Know Your Model**: Check if pre-normalized
2. **Consistent**: Normalize queries same as documents
3. **Verify**: Check norms after normalization
4. **Handle Zeros**: Safe normalization for edge cases
5. **Document**: Note normalization in code

## Performance

- Normalization: O(d) per vector
- One-time cost
- Negligible vs search cost
- Enable much faster similarity

## Pricing

Negligible processing cost; enables compute savings.