## Overview

Binary quantization converts high-dimensional floating-point vectors into binary representations (0s and 1s), enabling dramatic storage and computational savings for vector search applications while maintaining acceptable accuracy.

## How It Works

### Quantization Process

1. **Threshold Selection**: Choose value to split dimensions (often 0 or median)
2. **Bit Assignment**: Values above threshold = 1, below = 0
3. **Packing**: Pack 8 bits into bytes for efficient storage
4. **Indexing**: Build search index on binary vectors

### Example

```
Original vector: [0.5, -0.2, 0.8, -0.1, 0.3]
After quantization: [1, 0, 1, 0, 1]
Packed: 10101 (binary)
```

## Storage Benefits

### Compression Ratios

- **Float32**: 1024 dims × 4 bytes = 4,096 bytes per vector
- **Binary**: 1024 dims ÷ 8 = 128 bytes per vector
- **Compression**: 32x reduction

### Scale Impact

- 1M vectors: 4GB → 128MB
- 100M vectors: 400GB → 12.5GB
- 1B vectors: 4TB → 125GB

## Performance Characteristics

### Speed

- **Hamming Distance**: Ultra-fast bitwise operations
- **CPU Efficient**: No floating-point arithmetic
- **SIMD Friendly**: Parallel bit operations
- **Cache Efficient**: More vectors fit in cache

### Accuracy

- **Typical Recall**: 90-95% at k=10
- **Use Case Dependent**: Varies by data distribution
- **Refinement Possible**: Two-stage retrieval

## Implementation Approaches

### Statistical Binary Quantization

Available in pgvectorscale:
- Optimizes threshold per dimension
- Better accuracy than simple thresholding
- Minimal overhead

### Sign-Based Quantization

Simplest approach:
- Positive values → 1
- Negative values → 0
- Fast but less accurate

### Learned Quantization

- Train quantizer on representative data
- Optimize for specific similarity metrics
- Best accuracy, more complex

## Applications in 2026

### Local-First RAG

February 2026 implementations:
- SQLite with binary embeddings
- Hundreds of thousands of documents
- Commodity hardware
- No external dependencies

### Edge AI

- Mobile devices
- IoT sensors
- Browser-based AI
- Offline applications

### Large-Scale Systems

- Billions of vectors
- Cost optimization
- First-stage retrieval
- Multi-stage pipelines

## Two-Stage Retrieval

### Common Pattern

1. **Stage 1**: Binary search retrieves top-N candidates (N=100-1000)
2. **Stage 2**: Rescore with full-precision vectors
3. **Return**: Final top-k results

### Benefits

- Combines speed of binary with accuracy of full precision
- Reduces reranking computation
- Maintains high recall
- Optimizes cost

## Platform Support

### Native Support

- **pgvectorscale**: Statistical Binary Quantization
- **Azure AI Search**: Binary vector fields
- **Qdrant**: Binary quantization option
- **Custom**: Easy to implement

### Coming Soon

- More vector databases adding support
- Improved quantization algorithms
- Hardware acceleration

## Best Practices

### When to Use

- Storage costs significant
- Query latency critical
- Large-scale deployments
- Resource-constrained environments
- Two-stage retrieval acceptable

### When to Avoid

- Highest accuracy required
- Small datasets
- Plenty of resources
- Single-stage retrieval needed

### Optimization Tips

1. Test quantization on your specific data
2. Measure recall vs baseline
3. Tune retrieval parameters
4. Consider hybrid approaches
5. Monitor production metrics

## Future Directions

- Multi-bit quantization (2-4 bits)
- Adaptive quantization
- Hardware acceleration
- ML-optimized codebooks
- Dataset-specific tuning