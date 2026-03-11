## Overview

Vector quantization techniques compress high-precision embeddings into lower-precision representations, dramatically reducing storage and memory requirements.

## Types

### Scalar Quantization (SQ)

- Converts float32 to int8/uint8
- **4x compression** ratio
- Minimal accuracy loss
- Fast and simple

### Binary Quantization

- Reduces to 1-bit per dimension
- **32x compression**
- Hamming distance for search
- Best for high-dimensional vectors

### Product Quantization (PQ)

- Subvector clustering approach
- **8-64x compression**
- More complex but effective
- Widely used in production

## Benefits

- **Cost Reduction**: Lower storage costs
- **Faster Search**: Less data to process
- **Higher Throughput**: More vectors in memory
- **Scalability**: Fit larger datasets

## Tradeoffs

- Some recall degradation
- Quantization overhead
- Parameter tuning needed

## Support

- Qdrant: All types
- Milvus: SQ, PQ, BQ
- Weaviate: PQ, BQ
- Pinecone: SQ

## Pricing

Techniques, not products.