## Overview

Dot product similarity (also called scalar or inner product similarity) takes into account both the angle and the magnitude of vectors, providing a more comprehensive similarity metric that is faster to compute than cosine similarity for normalized vectors.

## How It Works

- Computed as: sum of element-wise products
- Formula: A · B = Σ(a_i * b_i)
- Considers both direction and magnitude
- Larger values indicate higher similarity
- Range depends on vector magnitudes

## Key Characteristics

- **Magnitude Sensitive**: Accounts for vector lengths
- **Directional**: Also considers angle between vectors
- **Fast Computation**: No division required
- **Comprehensive**: More information than cosine alone

## Relationship to Cosine Similarity

When vectors are normalized to unit length:
- Dot product ≈ Cosine similarity
- Using dot product on normalized vectors is equivalent to cosine
- Much faster since no magnitude calculation needed

## When to Use

- Vectors are normalized
- Both magnitude and direction matter
- Performance is critical
- Embedding models output normalized vectors
- Most modern embedding APIs

## Performance Advantages

- Faster than cosine similarity (no division)
- Simple multiplication and addition
- Efficient on modern hardware
- SIMD optimization friendly
- Lower computational overhead

## Best Practices

- Use with normalized embeddings for speed
- Check if your embedding model normalizes
- Default choice for most modern systems
- Monitor that vectors stay normalized

## Database Support

- All major vector databases
- Often called "inner product"
- Sometimes called "IP distance"
- Native support in:
  - Pinecone
  - Weaviate
  - Qdrant
  - Milvus
  - FAISS

## Comparison

- **vs. Cosine**: Faster for normalized vectors, equivalent results
- **vs. Euclidean**: Different information, depends on use case
- **vs. Others**: Generally preferred for embedding similarity

## Implementation Note

Which similarity function you can use depends on whether your vector embeddings are normalized—if your vectors are already normalized, use dot product similarity as it's much faster to compute.