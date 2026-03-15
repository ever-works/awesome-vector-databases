## Overview

Inverted File Index (IVF) is a fundamental vector indexing technique that partitions vectors into clusters using algorithms like k-means. During search, only the nearest clusters are examined, dramatically reducing the search space.

## How IVF Works

### Indexing Phase
1. **Clustering**: Run k-means to create centroids
2. **Assignment**: Assign each vector to its nearest centroid
3. **Inverted Lists**: Store vectors grouped by their centroid

### Query Phase
1. **Probe Selection**: Find k-nearest centroids to query (nprobe parameter)
2. **Candidate Retrieval**: Get all vectors from selected clusters
3. **Distance Computation**: Calculate distances to candidates
4. **Top-K Selection**: Return k-nearest vectors

## Key Parameters

### nlist (number of clusters)
- More clusters → more selective search
- Typical: sqrt(N) to 4*sqrt(N) where N is dataset size
- Trade-off: accuracy vs. memory

### nprobe (clusters to search)
- More probes → higher accuracy, slower search
- Typical: 1 to 10% of nlist
- Trade-off: speed vs. recall

## Advantages

- **Fast Search**: Reduces search space dramatically
- **Scalable**: Works with billions of vectors
- **Flexible**: Can be combined with other techniques
- **Tunable**: nprobe allows accuracy/speed trade-off

## Limitations

- **Accuracy**: May miss nearest neighbors in other clusters
- **Clustering Cost**: Initial k-means can be expensive
- **Memory**: Needs to store cluster assignments
- **Static**: Requires rebuilding for major data changes

## Common Variants

### IVF-FLAT
- Stores full vectors in inverted lists
- No compression, highest accuracy
- Large memory footprint

### IVF-PQ
- Compresses vectors with product quantization
- 4-5x memory compression
- Small accuracy loss
- Most popular variant

### IVF-SQ
- Uses scalar quantization for compression
- 4x compression with int8
- Good balance of accuracy and compression

## Performance Characteristics

- **Index Build Time**: O(N × iterations × k)
- **Memory**: O(N × d) for IVF-FLAT, less for compressed variants
- **Query Time**: O(nprobe × N/nlist × d)

## When to Use IVF

- **Best for**: Speed-critical applications with clustered data
- **Works well**: When vectors have natural clusters
- **Less ideal**: Uniformly distributed data
- **Combine with**: Product quantization for memory efficiency

## Implementation in Vector Databases

- **FAISS**: Extensive IVF implementations
- **Milvus**: IVF-FLAT, IVF-PQ, IVF-SQ
- **Pinecone**: Uses IVF-based indexing
- **Qdrant**: Supports IVF variants

## Comparison with HNSW

**IVF**: 
- Faster for speed-optimized scenarios
- Better memory efficiency with compression
- Lower accuracy without compression

**HNSW**:
- Higher accuracy and recall
- More memory intensive
- Better for complex vector spaces

## Hybrid Approaches

Combining IVF with HNSW:
- Use IVF for coarse filtering
- HNSW for fine-grained search
- Balances speed and accuracy

## Pricing

Not applicable (algorithmic technique implemented in various databases).