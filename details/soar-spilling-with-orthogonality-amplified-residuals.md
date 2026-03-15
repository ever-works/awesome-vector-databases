## Overview

SOAR (Spilling with Orthogonality-Amplified Residuals) is a major algorithmic advancement introduced by Google Research to enhance ScaNN's vector search capabilities. It introduces controlled redundancy to the vector index, significantly improving search efficiency.

## Key Innovation

Traditional partitioning assigns each vector to exactly one partition. SOAR allows vectors to "spill" into multiple partitions, creating redundancy that improves recall without proportional increases in search cost.

## How SOAR Works

### Spilling
- Vectors are assigned to multiple nearby partitions (not just one)
- Controlled redundancy improves chance of finding true neighbors
- Parameters control amount of spilling

### Orthogonality-Amplified Residuals
- Enhances quantization error modeling
- Amplifies orthogonal components in residual vectors
- Improves ranking accuracy for approximate search

## Performance Improvements

- Further 2-3x speedup over baseline ScaNN
- Maintains or improves accuracy
- Better recall at same query latency
- More efficient use of computational resources

## Technical Details

### Spilling Strategy
- Assign vector to k-nearest centroids (not just 1)
- Typical k=2 to 5 for good balance
- Storage increases by factor of k
- Query searches fewer partitions due to better coverage

### Residual Amplification
- Modifies how quantization residuals are computed
- Orthogonal error components are amplified
- Improves inner product approximation quality
- Works synergistically with anisotropic quantization

## Benefits Over Standard Partitioning

- **Higher Recall**: Less likely to miss neighbors due to partitioning
- **Faster Queries**: Can search fewer partitions for same recall
- **Robust**: Less sensitive to partition boundary effects
- **Scalable**: Improvements hold at billion-scale

## Trade-offs

**Advantages**:
- Significant speed improvements
- Better accuracy
- More stable performance

**Costs**:
- Increased index size (controlled by spilling factor)
- Slightly longer indexing time
- More complex implementation

## Use Cases

- Large-scale recommendation systems (billions of items)
- Real-time similarity search (low latency requirements)
- High-throughput scenarios (many concurrent queries)
- Applications where accuracy cannot be sacrificed for speed

## Implementation

Available in Google's ScaNN library:
```python
import scann

searcher = scann.scann_ops_pybind.builder(db, 10, "dot_product")
    .tree(
        num_leaves=2000,
        num_leaves_to_search=100,
        training_sample_size=250000)
    .score_ah(
        2,
        anisotropic_quantization_threshold=0.2)
    .reorder(100)
    .build()
```

SOAR features are integrated into the tree and scoring components.

## Comparison with Other Methods

**vs. Standard IVF**: Much better recall-speed tradeoff
**vs. HNSW**: Competitive performance with different characteristics
**vs. Original ScaNN**: 2-3x faster at same accuracy

## Research Impact

Published by Google Research, SOAR represents state-of-the-art in learned approximate search methods and has influenced subsequent research in efficient vector search.

## Availability

Open-source as part of ScaNN library on GitHub under Apache 2.0 license.

## Pricing

Free and open-source as part of ScaNN.