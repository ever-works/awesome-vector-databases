## Overview

Inner Product Similarity, also known as dot product, is a fundamental vector similarity metric that reports both the angle and magnitude between two vectors. It is widely used in recommendation systems, neural search, and machine learning.

## Mathematical Definition

For vectors a and b:
Inner Product = a · b = Σ(aᵢ × bᵢ)

## Key Properties

- **Magnitude-Aware**: Unlike cosine similarity, considers vector magnitudes
- **Fast Computation**: Simple multiplication and summation operations
- **Normalized Equivalence**: Equals cosine similarity when vectors are L2-normalized
- **Asymmetric**: Inner product can be different from reverse order (for non-normalized vectors)

## Relationship to Cosine Similarity

When vectors are normalized (||a|| = ||b|| = 1):
- Inner Product = Cosine Similarity
- This makes it a faster alternative to cosine when working with normalized embeddings

## Use Cases

- **Maximum Inner Product Search (MIPS)**: Finding items that maximize inner product with query
- **Recommendation Systems**: Matching user and item embeddings
- **Neural Search**: Similarity in learned embedding spaces
- **Ranking**: When magnitude carries semantic meaning

## Advantages

- Faster than cosine similarity (no normalization needed at query time)
- Preserves magnitude information when meaningful
- Directly optimizable in neural networks
- Natural fit for many ML objectives

## When to Use

- Working with pre-normalized embeddings (e.g., from many modern embedding models)
- Magnitude is semantically meaningful (e.g., confidence scores)
- Performance is critical and vectors are normalized
- Training models with inner product objectives

## Comparison with Other Metrics

**vs. Cosine**: Same for normalized vectors, faster to compute
**vs. Euclidean**: Considers angle and magnitude differently, better for learned embeddings
**vs. Hamming**: Works with continuous values, not discrete

## Implementation in Vector Databases

Supported by major vector databases including Pinecone, Milvus, Qdrant, and Weaviate under names like "dot product", "inner product", or "IP".

## Pricing

Not applicable (mathematical concept).