## Overview

Semantic chunking splits text by grouping sentences based on the semantic similarity of their embeddings, detecting topic shifts mathematically using embedding similarity thresholds.

## How It Works

1. Generate embeddings for each sentence
2. Calculate similarity between consecutive sentences
3. Detect significant similarity drops (topic shifts)
4. Split at points where similarity difference exceeds threshold
5. Default: 95th percentile threshold

## Example Detection

- Most sentences: 0.85 similar
- Two consecutive sentences: 0.65 similar
- Split triggered due to significant drop
- Indicates topic boundary

## Advantages

- Content-aware segmentation
- Respects natural topic boundaries
- Adapts to content structure
- Preserves semantic coherence within chunks
- Language model aware

## Challenges

### Performance Considerations
- Vecta 2026 benchmark: 54% accuracy
- Produces very small chunks (avg 43 tokens)
- Higher embedding costs
- More complex implementation

### Practical Issues
- Requires embedding generation for all sentences
- Computational overhead
- Variable chunk sizes
- May need post-processing to meet size constraints

## When to Use

- Content with clear topic shifts
- High-budget applications
- Precision-critical use cases
- Research and experimentation
- Documents with natural semantic boundaries

## When to Avoid

- Cost-sensitive applications
- Need for consistent chunk sizes
- Simple, well-structured content
- Production systems requiring proven reliability

## Implementation Approaches

- LangChain SemanticChunker variants:
  - LLMSemanticChunker: 0.919 recall
  - ClusterSemanticChunker: 0.913 recall
- Custom embedding-based implementations
- Threshold tuning required

## Best Practices

- Test against simpler methods first
- Monitor chunk size distribution
- Consider hybrid approaches
- Budget for embedding costs
- Validate against metrics

## 2026 Recommendation

Move to semantic chunking only if metrics show need for extra performance and budget allows costs; start with RecursiveCharacterTextSplitter for most use cases.