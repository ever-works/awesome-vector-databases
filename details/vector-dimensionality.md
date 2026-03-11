## Overview

Vector dimensionality refers to the number of components (dimensions) in an embedding vector. It's a fundamental parameter affecting accuracy, storage, compute costs, and system performance.

## Common Dimensionalities (2026)

- **Small**: 128-384 dimensions (fast, compact)
- **Standard**: 512-768 dimensions (most sentence transformers)
- **Large**: 1024-1536 dimensions (OpenAI, Cohere)
- **Very Large**: 2048-4096 dimensions (specialized models)

## Trade-offs

### Higher Dimensions
**Advantages:**
- More expressive representations
- Better capture of nuanced information
- Higher accuracy on complex tasks

**Disadvantages:**
- More storage (4x for 2048 vs 512)
- Slower similarity computations
- Higher memory bandwidth requirements
- Increased costs

### Lower Dimensions
**Advantages:**
- Faster search
- Lower storage costs
- Better cache efficiency
- Reduced bandwidth

**Disadvantages:**
- Less expressive
- May miss subtle distinctions
- Lower accuracy on complex tasks

## Optimization Techniques

### Matryoshka Embeddings
Enable truncating dimensions (e.g., 1024 → 256) with minimal accuracy loss through specialized training.

### Dimensionality Reduction
- PCA: Project to lower dimensions
- Matryoshka: Use early dimensions only
- Adaptive: Choose dimensions per use case

## Storage Impact

1M vectors at different dimensions:
- 128D: ~512 MB
- 384D: ~1.5 GB
- 768D: ~3 GB
- 1536D: ~6 GB
- 3072D: ~12 GB

## Performance Considerations

Higher dimensions:
- Increase memory bandwidth requirements
- Slow down similarity computations
- Require more powerful hardware
- Cost more in cloud deployments

## Best Practices

- Start with model's native dimensions
- Consider Matryoshka for flexibility
- Test lower dimensions for cost savings
- Match dimensions to task complexity
- Monitor accuracy vs cost trade-offs

## 2026 Recommendations

For most applications:
- Use 768-1024 dimensions as baseline
- Leverage Matryoshka for cost optimization
- Test truncated dimensions on your data
- Combine with quantization for maximum savings

## Curse of Dimensionality

Very high dimensions can suffer from:
- Increased sparsity
- Distance concentration
- Overfitting in similarity

Generally, 1536-2048 dimensions is practical limit for most applications.