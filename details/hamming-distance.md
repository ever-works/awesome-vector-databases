## Overview

Hamming Distance is a distance metric for binary vectors that counts the number of positions at which the corresponding bits are different. It's the primary distance metric used with binary quantized embeddings.

## How Hamming Distance Works

For two binary vectors:
1. Perform XOR operation (bits differ where XOR = 1)
2. Count the number of 1s (popcount)
3. This count is the Hamming distance

### Example

```
Vector A: 10110
Vector B: 10011
XOR:      00101  (2 bits differ)
Hamming Distance = 2
```

## Computational Efficiency

### Hardware Acceleration

Modern CPUs have hardware instructions for:
- **XOR**: Single cycle operation
- **popcount**: Dedicated hardware instruction
- Can process 64 or 128 bits at once

### Performance Benefits

- 10-100x faster than float vector comparisons
- Enables real-time search on billions of vectors
- Minimal memory bandwidth requirements

## Use with Binary Quantization

Hamming distance is the natural metric for binary quantized embeddings:
- Convert embeddings to binary (1 bit per dimension)
- Store compactly (32x compression)
- Search using Hamming distance
- Optionally rescore top results with full precision

## Properties

### Metric Properties

- **Non-negativity**: d(a,b) ≥ 0
- **Identity**: d(a,b) = 0 iff a = b
- **Symmetry**: d(a,b) = d(b,a)
- **Triangle inequality**: d(a,c) ≤ d(a,b) + d(b,c)

## Comparison with Other Metrics

**vs Euclidean Distance**:
- Much faster to compute
- Only works with binary vectors
- Lower precision

**vs Cosine Similarity**:
- Simpler calculation
- Binary only
- Used in different contexts

## Use Cases

- Binary quantized vector search
- First-stage retrieval (before rescoring)
- Massive-scale similarity search
- Real-time search applications
- Error detection and correction

## Implementations

Available in:
- Most vector databases (Qdrant, Milvus, Weaviate)
- NumPy: `np.count_nonzero(a != b)`
- SciPy: `scipy.spatial.distance.hamming`
- Custom SIMD implementations

## Pricing

Free - algorithmic concept widely implemented.