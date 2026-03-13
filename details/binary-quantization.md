## Overview

Binary Quantization is an extreme compression technique that converts each vector dimension to a single bit (0 or 1), achieving up to 32x memory reduction compared to 32-bit floats and enabling ultra-fast similarity search using Hamming distance.

## How Binary Quantization Works

### Quantization Process

1. **Threshold**: Determine a threshold (often 0 or mean value)
2. **Binarize**: Convert each dimension to 1 if above threshold, 0 otherwise
3. **Pack**: Pack bits efficiently for storage
4. **Store**: Store binary vectors (1 bit per dimension)

### Search Process

1. Binarize query vector using same threshold
2. Compute Hamming distance (count differing bits)
3. Use XOR and popcount for ultra-fast computation
4. Optionally rescore top candidates with original vectors

## Memory Reduction

- **32-bit float → 1 bit**: 32x compression
- Example: 768-dim vector: 3,072 bytes → 96 bytes
- Enables keeping billions of vectors in memory

## Performance Benefits

### Speed

- Hamming distance via XOR + popcount: extremely fast
- Modern CPUs have hardware popcount instructions
- Can process vectors 10-100x faster than float comparisons

### Accuracy Considerations

- Accuracy loss more significant than PQ or SQ
- Works well with models trained for binary embeddings
- Typically 5-15% recall reduction vs full precision

## When Binary Quantization Works Best

### Model Characteristics

- High-dimensional embeddings (768+)
- Models with well-distributed values
- Embeddings specifically trained for binary quantization

### Use Cases

- First-stage retrieval (rerank with full precision)
- Massive-scale search (billions of vectors)
- Memory-constrained environments
- Real-time search requirements

## Limitations

- Significant accuracy loss for some datasets
- Not suitable for all embedding models
- Requires careful threshold selection
- May need rescoring step

## Modern Implementations

Many embedding models now support Matryoshka Representation Learning combined with binary quantization for flexible compression-accuracy trade-offs.

## Pricing

Implemented in vector databases (Qdrant, Milvus, Weaviate, etc.)