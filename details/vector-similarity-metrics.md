## Overview

The three main, commonly used similarity metrics are cosine similarity, dot product, and Euclidean distance, though Manhattan distance is also frequently used. Choosing the right metric is critical for vector search performance and accuracy.

## Core Metrics

### Cosine Similarity

**Definition**: Measures the angle between two vectors, ranging from -1 to 1.

**Formula**: 
```
cosine_similarity = (A · B) / (||A|| × ||B||)
```

**Characteristics**:
- **Magnitude-independent**: Only considers direction
- **Score**: 1 = perfect similarity, 0 = orthogonal, -1 = opposite
- **Normalized**: Not affected by vector length

**Best For**:
- Text similarity and semantic search
- When direction matters more than magnitude
- Normalized embeddings
- High-dimensional spaces

### Dot Product (Inner Product)

**Definition**: Measures both directional similarity AND magnitude.

**Formula**:
```
dot_product = A · B = Σ(ai × bi)
```

**Characteristics**:
- **Magnitude-sensitive**: Larger vectors score higher
- **Fast**: No normalization required
- **Equivalent to cosine for normalized vectors**

**Best For**:
- Recommendation systems (magnitude = importance)
- Scoring and ranking
- When vector magnitude carries semantic meaning

### Euclidean Distance (L2)

**Definition**: Straight-line distance between two points in space.

**Formula**:
```
euclidean = √(Σ(ai - bi)²)
```

**Characteristics**:
- **Geometric distance**: Actual spatial separation
- **Scale-sensitive**: Affected by magnitude
- **Range**: 0 to ∞ (lower is more similar)

**Best For**:
- Clustering
- Anomaly detection
- When absolute differences matter
- Low-to-medium dimensional data

### Manhattan Distance (L1)

**Definition**: Sum of absolute differences along each dimension.

**Formula**:
```
manhattan = Σ|ai - bi|
```

**Characteristics**:
- **Grid-based**: Sum of axis-aligned distances
- **Outlier-robust**: Less sensitive to extreme values
- **Range**: 0 to ∞

**Best For**:
- High-dimensional data
- When outliers are present
- Sparse vectors
- Grid-like data structures

## Comparison Table

| Metric | Direction | Magnitude | Normalized | Range | Complexity |
|--------|-----------|-----------|------------|-------|------------|
| Cosine | ✓ | ✗ | Yes | [-1, 1] | Medium |
| Dot Product | ✓ | ✓ | No | [-∞, ∞] | Low |
| Euclidean | ✓ | ✓ | No | [0, ∞] | Medium |
| Manhattan | ✓ | ✓ | No | [0, ∞] | Low |

## Choosing the Right Metric

### Basic Rule of Thumb

Match the similarity metric to the one used to train your embedding model.

### Use Case Guide

**Semantic Search / NLP**:
- Primary: **Cosine Similarity**
- Reason: Direction captures semantic meaning

**Image Retrieval**:
- Primary: **Cosine or Euclidean**
- Depends on: Model training approach

**Recommendation Systems**:
- Primary: **Dot Product**
- Reason: Magnitude can represent importance/popularity

**Clustering**:
- Primary: **Euclidean**
- Alternative: Manhattan for robustness

**Anomaly Detection**:
- Primary: **Euclidean**
- Reason: Absolute distance from normal

## Normalized vs Non-Normalized

### When Vectors are Normalized (unit length):
- Cosine similarity = Dot product
- Faster computation with dot product
- Most modern embedding models output normalized vectors

### When Vectors are NOT Normalized:
- Use Cosine for direction-only comparison
- Use Dot Product for magnitude+direction
- Euclidean sensitive to scale

## Implementation Examples

### Python (NumPy)

```python
import numpy as np

# Cosine Similarity
def cosine_similarity(a, b):
    return np.dot(a, b) / (np.linalg.norm(a) * np.linalg.norm(b))

# Euclidean Distance
def euclidean_distance(a, b):
    return np.linalg.norm(a - b)

# Dot Product
def dot_product(a, b):
    return np.dot(a, b)

# Manhattan Distance
def manhattan_distance(a, b):
    return np.sum(np.abs(a - b))
```

## Database Support

Most vector databases support multiple metrics:
- Cosine, Euclidean, Dot Product (universal)
- Manhattan, Hamming, Jaccard (common)
- Custom metrics (some platforms)

## Performance Considerations

**Speed** (fastest to slowest):
1. Dot Product
2. Manhattan
3. Cosine (requires normalization)
4. Euclidean (requires square root)

**Accuracy Trade-offs**:
- More complex metrics → better semantic capture
- Simpler metrics → faster computation
- Choose based on latency requirements

## Pricing

Similarity metrics are mathematical operations, free to implement.