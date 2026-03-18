## Overview

Embedding dimension selection significantly impacts storage costs, query latency, and retrieval accuracy. Modern techniques like Matryoshka embeddings offer flexibility.

## Common Embedding Dimensions

- **384**: Compact models (all-MiniLM-L6-v2)
- **768**: BERT-base, many sentence transformers
- **1024**: Larger transformer models
- **1536**: OpenAI text-embedding-3-small
- **3072**: OpenAI text-embedding-3-large

## Trade-offs

**Higher Dimensions**:
- Better semantic capture
- Higher accuracy
- More storage (4 bytes × dimensions)
- Slower distance calculations
- Higher costs

**Lower Dimensions**:
- Faster queries
- Less storage
- Lower costs
- May lose semantic nuance

## Matryoshka Embeddings

Allow flexible dimension usage from same model:
- Train once, use at multiple sizes
- Truncate to smaller dimensions
- 384-dim truncation often maintains 95%+ quality
- Supported by OpenAI, Nomic, Alibaba models

## Dimension Reduction Techniques

**PCA (Principal Component Analysis)**:
- Linear projection to lower dimensions
- Preserves maximum variance
- Requires fitting on dataset

**Random Projection**:
- Fast, simple dimensionality reduction
- Johnson-Lindenstrauss lemma guarantees

**Autoencoder**:
- Neural network compression
- Can learn non-linear reductions
- Requires training

## Cost Impact Example

1M vectors:
- 384 dims: 1.5 GB
- 768 dims: 3.0 GB
- 1536 dims: 6.0 GB
- 3072 dims: 12 GB

With quantization (int8):
- Divide by 4 for memory

## Selection Guidelines

**For General Use**: 768-1024 dimensions

**For Cost-Sensitive**: 384 dimensions or Matryoshka truncation

**For Maximum Quality**: 1536-3072 dimensions

**For Specialized Domains**: Test on your data

## Testing Methodology

1. Choose evaluation dataset
2. Test multiple dimensions
3. Measure retrieval quality (Recall@K)
4. Measure query latency
5. Calculate storage costs
6. Find optimal trade-off point

## Best Practices

1. Don't assume bigger is better
2. Test with your actual queries
3. Consider Matryoshka models for flexibility
4. Monitor metrics over time
5. Re-evaluate if workload changes
6. Use quantization to reduce costs
7. Benchmark before committing