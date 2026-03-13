## Overview

Scalar Quantization (SQ) is a simpler compression technique than Product Quantization that reduces the precision of each vector component, typically from 32-bit floating point to 8-bit integers, achieving 4x memory reduction.

## How Scalar Quantization Works

### Quantization Process

1. **Find Range**: Determine min and max values for each dimension
2. **Map**: Map the continuous range to discrete integer values (e.g., 0-255 for 8-bit)
3. **Encode**: Convert each float component to its quantized integer
4. **Store**: Store compact 8-bit representations

### Search Process

1. Quantize query vector using same mapping
2. Compute approximate distances using quantized vectors
3. Optionally rerank top candidates using original vectors

## Memory Reduction

- **32-bit float → 8-bit int**: 4x compression
- **32-bit float → 4-bit int**: 8x compression
- Example: 768-dim vector: 3,072 bytes → 768 bytes (8-bit) or 384 bytes (4-bit)

## Variants

### Asymmetric Scalar Quantization

- Database vectors: quantized
- Query vectors: kept in full precision
- Better accuracy than symmetric quantization

### Per-Dimension vs Global

- **Per-dimension**: Different min/max for each dimension
- **Global**: Single min/max across all dimensions

## Trade-offs

**Advantages**:
- Simple to implement
- Minimal accuracy loss (1-2% typical)
- Fast compression and decompression
- Works well with modern SIMD instructions

**Disadvantages**:
- Less compression than Product Quantization
- Still requires significant memory for large datasets

## Comparison with Other Methods

**vs Product Quantization**:
- Less compression but better accuracy
- Simpler and faster
- No training required

**vs Binary Quantization**:
- Better accuracy but less compression

## Use Cases

- When 4x compression is sufficient
- Applications requiring high accuracy
- Real-time search scenarios
- When simplicity is valued

## Pricing

Implemented in most vector databases (Qdrant, Milvus, Weaviate, etc.)