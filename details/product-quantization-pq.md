## Overview

Product Quantization (PQ) is a vector compression technique that splits high-dimensional vectors into subvectors and quantizes each subvector independently. This achieves significant memory reduction (often 32x or more) while enabling approximate similarity search.

## How Product Quantization Works

### Compression Process

1. **Split**: Divide each d-dimensional vector into m subvectors
2. **Learn Codebooks**: Train a codebook (lookup table) for each subvector using k-means
3. **Quantize**: Replace each subvector with its nearest codebook entry's index
4. **Store**: Store only the compact codes instead of full vectors

### Search Process

1. Quantize query vector using same splitting
2. Pre-compute distances between query subvectors and all codebook entries
3. Approximate full vector distances using lookup table
4. Return top-k results

## Memory Reduction

Typical compression:
- Original: 768 dimensions × 4 bytes = 3,072 bytes per vector
- PQ (m=96, k=256): 96 bytes per vector
- **Compression ratio**: ~32x

## Variants

### IVF-PQ

Combines Inverted File clustering with Product Quantization for both speed and compression.

### OPQ (Optimized Product Quantization)

Applies a learned rotation before quantization to reduce quantization error.

### Additive Quantization

Uses sum of multiple codebook entries for better accuracy.

## Trade-offs

**Advantages**:
- Significant memory reduction
- Faster similarity computation
- Enables larger datasets in memory

**Disadvantages**:
- Loss of accuracy (quantization error)
- Requires training phase
- Not suitable for exact search

## Configuration Parameters

- **m**: Number of subvectors (segments)
- **nbits**: Bits per code (determines codebook size: k=2^nbits)

## Use Cases

- Large-scale vector search (billions of vectors)
- Memory-constrained environments
- When some accuracy loss is acceptable
- Reducing infrastructure costs

## Pricing

Implemented in open-source libraries (FAISS, ScaNN, etc.)