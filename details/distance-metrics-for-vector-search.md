## Common Distance Metrics

**Cosine Similarity**:
- Measures angle between vectors
- Range: [-1, 1] (or [0, 1] for positive)
- Ignores magnitude
- **Best for**: Text embeddings, semantic similarity
- **Formula**: cos(θ) = (A·B) / (||A|| ||B||)

**Euclidean Distance (L2)**:
- Straight-line distance
- Considers magnitude
- Range: [0, ∞)
- **Best for**: Spatial data, image embeddings
- **Formula**: ||A - B|| = sqrt(Σ(ai - bi)²)

**Dot Product**:
- Inner product of vectors
- Fast to compute
- Range: (-∞, ∞)
- **Best for**: Normalized vectors, efficiency-critical
- **Formula**: A·B = Σ(ai × bi)

**Manhattan Distance (L1)**:
- Sum of absolute differences
- More robust to outliers
- Range: [0, ∞)
- **Best for**: High-dimensional sparse data
- **Formula**: Σ|ai - bi|

## When to Use Each

**Cosine Similarity**: Default for text/semantic search
- Sentence transformers
- Document similarity
- Semantic search

**Euclidean**: When magnitude matters
- Image embeddings
- Facial recognition
- Spatial coordinates

**Dot Product**: For speed
- Normalized embeddings
- Real-time systems
- Simple, fast computation

**Manhattan**: Special cases
- Sparse high-dimensional data
- Outlier robustness needed

## Normalization Impact

**With Normalized Vectors**:
- Cosine ≈ Dot Product
- Euclidean ≈ Angular distance
- Most models normalize internally

**Without Normalization**:
- Metrics behave differently
- Cosine ignores magnitude
- Euclidean considers it

## Performance Characteristics

**Speed** (fastest to slowest):
1. Dot Product
2. Cosine (with pre-normalized)
3. Manhattan
4. Euclidean

**Most Common in Production**:
- Text: Cosine (90%)
- Images: Euclidean or Cosine
- Hybrid: Dot product on normalized

## Database Support

| Database | Cosine | Euclidean | Dot Product | Manhattan |
|----------|--------|-----------|-------------|----------|
| Pinecone | ✓ | ✓ | ✓ | - |
| Weaviate | ✓ | ✓ | ✓ | ✓ |
| Qdrant | ✓ | ✓ | ✓ | ✓ |
| Milvus | ✓ | ✓ | ✓ | ✓ |
| pgvector | ✓ | ✓ | ✓ | - |

## Best Practices

1. Use what embedding model recommends
2. Cosine for text (safe default)
3. Normalize if using dot product
4. Test on your data
5. Stay consistent across pipeline
6. Consider computation cost

## Common Mistakes

- Mixing metrics in same system
- Not normalizing for dot product
- Using Euclidean for text
- Ignoring model recommendations
- Not testing alternatives