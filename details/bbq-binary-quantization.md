## Overview

BBQ (derived from RaBitQ) is Elasticsearch and Lucene's implementation of 1-bit binary quantization for vector search, providing extreme compression while maintaining search accuracy through mathematical guarantees.

## Origin and Naming

BBQ is Elasticsearch's adaptation of the RaBitQ algorithm with minor modifications for integration with Lucene's HNSW implementation. The algorithm was developed by researchers at NTU and adopted by major search platforms.

## Technical Foundation

### 1-Bit Quantization
- Reduces each dimension from 32 bits (float) to 1 bit (sign)
- **32x compression**: 1024-dim vector: 4KB → 128 bytes
- Uses sign information only
- Mathematical optimality guarantees

### Theoretical Guarantees
- **Asymptotically optimal error bound** for distance estimation
- **Inner product preservation** for similarity computation
- **Reliable ordering** for nearest neighbor search
- **Reranking support** with corrective factors

## How It Works

### Quantization Process

1. **Normalization**:
   - Normalize input vectors to unit length
   - Ensures consistent scale

2. **Random Rotation**:
   - Apply random orthogonal transformation
   - Distributes information across dimensions
   - Rotation matrix computed once, reused

3. **Sign Extraction**:
   - Store sign bit for each dimension
   - 1 bit per dimension
   - Results in binary vector

4. **Corrective Factors**:
   - Store small correction term per vector
   - Improves distance estimation
   - Minimal additional storage (~8 bytes)

### Search Process

1. **Query Quantization**:
   - Apply same rotation to query
   - Extract sign vector

2. **Hamming Distance**:
   - XOR between binary vectors
   - POPCNT for bit counting
   - Hardware-accelerated (CPU instruction)

3. **Distance Estimation**:
   - Use Hamming distance + corrective factors
   - Estimate original cosine similarity
   - Reliable for ranking

4. **Reranking** (optional):
   - Retrieve top-k candidates
   - Rerank with full precision
   - Improves final accuracy

## Advantages

### Storage Efficiency
- **32x compression** vs float32
- No codebook storage required
- Minimal metadata overhead
- Scales to billions of vectors

### Computational Efficiency
- **Hamming distance**: Single CPU instruction
- **SIMD optimization**: Process multiple comparisons
- **Cache-friendly**: Binary vectors fit in cache
- **Low memory bandwidth**: 32x less data movement

### Mathematical Properties
- **Optimal error bounds**: Provably good approximation
- **No training required**: Deterministic process
- **Rotation-based**: Distributes information uniformly
- **Inner product preservation**: Maintains similarity structure

## Performance Characteristics

### Compression
- **Storage**: 32x reduction
- **Example**: 1 billion 1024-dim vectors
  - Original: 4TB
  - BBQ: 125GB + corrections
  - Total: ~140GB (28x effective compression)

### Speed
- **Hamming distance**: Nanoseconds per comparison
- **Throughput**: Millions of comparisons/second
- **Latency**: Sub-millisecond for large datasets
- **Scalability**: Linear with database size

### Accuracy
- **Recall**: 95-98% @ k=10 (typical)
- **With reranking**: 98-99.5% recall
- **Trade-off**: Adjustable via candidate set size

## Integration with Elasticsearch

### HNSW Index
- BBQ integrated with Lucene's HNSW
- Binary vectors stored in graph
- Fast graph traversal
- Efficient approximate search

### Query API
```json
GET /my-index/_search
{
  "knn": {
    "field": "vector",
    "query_vector": [...],
    "k": 10,
    "num_candidates": 100
  }
}
```

### Index Settings
```json
PUT /my-index
{
  "mappings": {
    "properties": {
      "vector": {
        "type": "dense_vector",
        "dims": 1024,
        "index": true,
        "similarity": "cosine",
        "index_options": {
          "type": "hnsw",
          "m": 16,
          "ef_construction": 100
        },
        "quantization": {
          "type": "bbq"
        }
      }
    }
  }
}
```

## Use Cases

### Ideal For
- Large-scale semantic search
- Document retrieval
- Image similarity search
- Recommendation systems
- High-dimensional embeddings
- Cost-sensitive deployments

### When to Use BBQ
- Dataset > 10 million vectors
- Storage costs significant
- High query volume
- Recall requirements: 95%+
- Cosine similarity metric

## Comparison with Alternatives

### vs Scalar Quantization (SQ8)
- BBQ: 32x compression
- SQ8: 4x compression
- BBQ: Faster search
- SQ8: Better accuracy

### vs Product Quantization (PQ)
- BBQ: No training required
- PQ: Higher compression possible
- BBQ: Faster search
- PQ: More complex setup

### vs Dense (No Quantization)
- BBQ: 32x less storage
- Dense: Perfect accuracy
- BBQ: Faster search
- Dense: Simpler implementation

## Best Practices

### Configuration
- Use with HNSW index
- Set appropriate num_candidates
- Enable reranking for high accuracy
- Monitor recall metrics
- Tune based on use case

### Optimization
- **num_candidates**: 2-5x k for good recall
- **reranking**: Enable for >98% recall
- **HNSW parameters**: Tune m and ef_construction
- **Hardware**: CPU with AVX2/AVX-512

### Monitoring
- Track recall@k metrics
- Measure query latency
- Monitor storage usage
- Compare with full precision
- A/B test configurations

## Limitations

- **Metric constraint**: Best for cosine similarity
- **Accuracy**: Not perfect (95-98% typical)
- **Euclidean**: Less optimal for L2 distance
- **Reranking**: May need for high recall

## Implementation Details

### Rotation Matrix
- Computed once per index
- Stored as metadata
- Applied to all vectors
- Reused for queries

### Corrective Factors
- Per-vector correction term
- ~8 bytes per vector
- Improves distance estimation
- Used in scoring

### Hardware Acceleration
- **POPCNT**: Bit counting instruction
- **SIMD**: Parallel processing
- **AVX-512**: 512-bit operations
- **Cache**: Binary vectors fit well

## Research Background

Based on RaBitQ research from NTU (National Taiwan University):
- Published 2024
- Theoretical foundations in coding theory
- Implemented in major search platforms
- Active area of research

## Future Directions

- Multi-bit extensions
- Adaptive quantization
- Better corrective factors
- Hardware-specific optimizations
- Integration with other indexes

## Related Technologies

- **RaBitQ**: Original algorithm
- **Binary Embeddings**: Related concept
- **Hamming Distance**: Core primitive
- **Product Quantization**: Alternative approach
- **Scalar Quantization**: Simpler method

## Pricing

Available in:
- Elasticsearch (open source)
- Elastic Cloud (managed service)
- Pricing based on Elasticsearch licensing

## Resources

- Elastic blog: RaBitQ explainer
- Lucene implementation
- Research papers on RaBitQ
- Elasticsearch documentation
- Performance benchmarks