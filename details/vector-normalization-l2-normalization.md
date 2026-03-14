## Overview

L2 normalization scales embedding vectors to a consistent magnitude by converting them to unit length. This ensures all vectors lie on the surface of a unit sphere, making similarity measures focus purely on direction rather than magnitude.

## What is L2 Normalization?

The standard approach adjusts each vector so its Euclidean length (L2 norm) becomes 1. This is done by dividing each component of the vector by the vector's original L2 norm.

## Mathematical Definition

### L2 Norm (Euclidean Length)

```
||v|| = √(v₁² + v₂² + ... + vₙ²)
```

### Normalized Vector

```
v_normalized = v / ||v||
```

## Example

**Original vector**: [3, 4]
- L2 norm: √(3² + 4²) = √25 = 5
- Normalized: [3/5, 4/5] = [0.6, 0.8]
- Verify: √(0.6² + 0.8²) = √(0.36 + 0.64) = 1 ✓

## Why Normalize Embeddings?

### Key Benefits

1. **Removes Magnitude Influence**: Focuses on direction (semantic meaning)
2. **Cosine = Dot Product**: Faster computation with normalized vectors
3. **Consistent Scaling**: All vectors have equal importance
4. **Improved Similarity**: Better semantic comparisons

### Mathematical Equivalence

For normalized vectors A and B:
```
cosine_similarity(A, B) = dot_product(A, B)
```

This enables:
- Faster computation (no division)
- Hardware optimization
- Simplified distance calculations

## When to Normalize

### You SHOULD Normalize When:

- Using cosine similarity for comparison
- Vector magnitude doesn't carry semantic meaning
- Comparing embeddings from different sources
- Model doesn't output normalized embeddings (BERT, RoBERTa)
- Building semantic search systems

### You DON'T Need to Normalize When:

- Model explicitly outputs normalized embeddings (some sentence-transformers)
- Using Euclidean distance and magnitude matters
- Magnitude carries important information
- Vectors already unit-length

## Implementation

### Python with NumPy

```python
import numpy as np

def normalize_l2(vector):
    norm = np.linalg.norm(vector, ord=2)
    # Add epsilon to avoid division by zero
    epsilon = 1e-12
    return vector / (norm + epsilon)

# Batch normalization
def normalize_batch(vectors):
    norms = np.linalg.norm(vectors, axis=1, keepdims=True)
    return vectors / (norms + 1e-12)
```

### PyTorch

```python
import torch
import torch.nn.functional as F

# Single vector
normalized = F.normalize(vector, p=2, dim=0)

# Batch of vectors
normalized_batch = F.normalize(vectors, p=2, dim=1)
```

### TensorFlow

```python
import tensorflow as tf

normalized = tf.math.l2_normalize(vector, axis=-1)
```

### Scikit-learn

```python
from sklearn.preprocessing import normalize

normalized = normalize(vectors, norm='l2')
```

## Important Considerations

### Zero Vectors

**Problem**: Division by zero if norm is 0 (all-zeros embedding)

**Solution**: Add epsilon (tiny value like 1e-12) to denominator

```python
normalized = vector / (norm + 1e-12)
```

### Near-Zero Vectors

**Problem**: Very small norms can cause numerical instability

**Solution**: 
- Check if norm < threshold
- Handle specially or filter out

### Numerical Precision

**Problem**: Floating-point errors in high dimensions

**Solution**:
- Use float32 or float64
- Verify norm ≈ 1 after normalization

## Model-Specific Behavior

### Models That DON'T Normalize Output

- BERT (raw pooler output)
- RoBERTa
- GPT (embeddings)
- Custom models (check documentation)

**Action**: Apply L2 normalization before similarity computation

### Models That DO Normalize Output

- Sentence-Transformers (many models)
- OpenAI text-embedding-ada-002
- Cohere embeddings
- Some fine-tuned models

**Action**: Normalization may be redundant (verify documentation)

## Performance Impact

### Computation Cost

- **Normalization**: O(d) where d = dimensions
- **Amortized**: One-time cost during indexing
- **Benefit**: Faster similarity computation

### Storage

No additional storage required (same dimensions)

## Best Practices

1. **Check Model Output**: Verify if embeddings are already normalized
2. **Add Epsilon**: Prevent division by zero
3. **Normalize Once**: During indexing, not every query
4. **Batch Process**: Normalize multiple vectors together for efficiency
5. **Verify**: Check norm ≈ 1 after normalization
6. **Document**: Clearly indicate if vectors are normalized

## Common Errors

### Not Normalizing When Required

```python
# WRONG: Using cosine similarity without normalization
similarity = np.dot(embedding1, embedding2)  # Not equivalent to cosine!

# RIGHT: Normalize first
emb1_norm = normalize_l2(embedding1)
emb2_norm = normalize_l2(embedding2)
similarity = np.dot(emb1_norm, emb2_norm)  # Now equivalent to cosine
```

### Normalizing Already Normalized Vectors

```python
# WRONG: Double normalization
embedding = model.encode(text)  # Already normalized
embedding = normalize_l2(embedding)  # Redundant!

# RIGHT: Check documentation first
```

## Pricing

Normalization is a mathematical operation, free to implement.