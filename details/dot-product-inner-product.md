## Overview

Dot product (inner product) is a similarity metric that sums the element-wise products of two vectors, widely used in vector databases for its computational efficiency.

## Formula

Dot Product = Σ(Ai × Bi)

## Characteristics

- **Unnormalized**: Sensitive to magnitude
- **Higher values**: More similar
- **Efficient**: Fast computation
- **For normalized vectors**: Equivalent to cosine similarity

## Use Cases

- Pre-normalized embeddings
- When magnitude conveys information
- Maximum Inner Product Search (MIPS)
- Fast approximate search

## Vector Database Support

- Milvus: IP (Inner Product)
- Pinecone: dotproduct metric
- Weaviate: dot product
- pgvector: inner product operator

## Pricing

Algorithm, no licensing costs.