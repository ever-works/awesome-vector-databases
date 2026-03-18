## Vector Index Types

Vector indexes are data structures that enable efficient similarity search. Different index types offer different trade-offs.

## Main Index Types

### Flat Index
- **Method**: Brute-force search through all vectors
- **Accuracy**: 100% (exact search)
- **Speed**: Slowest (O(n))
- **Memory**: Full vectors in memory
- **Best for**: < 10K vectors, baseline comparisons

### IVF (Inverted File Index)
- **Method**: Clusters vectors, searches relevant clusters
- **Accuracy**: 90-99% (approximate)
- **Speed**: 10-100x faster than Flat
- **Memory**: Moderate
- **Best for**: Millions of vectors, memory-constrained environments

### HNSW (Hierarchical Navigable Small World)
- **Method**: Multi-layer proximity graph
- **Accuracy**: 95-99.9% (excellent recall)
- **Speed**: Very fast queries
- **Memory**: High (stores graph)
- **Best for**: Up to hundreds of millions, real-time apps

### DiskANN
- **Method**: Disk-based graph index
- **Accuracy**: 95-99%
- **Speed**: Fast (with SSD)
- **Memory**: Low (mostly on disk)
- **Best for**: Billions of vectors, cost-sensitive deployments

### LSH (Locality-Sensitive Hashing)
- **Method**: Hash similar vectors to same buckets
- **Accuracy**: 80-95%
- **Speed**: Fast
- **Memory**: Low
- **Best for**: Very large scale, speed critical

## Comparison Matrix

| Index Type | Query Speed | Build Time | Memory | Accuracy | Scale Limit |
|------------|-------------|------------|--------|----------|-------------|
| Flat | Slow | Instant | High | Perfect | 10K |
| IVF | Fast | Minutes | Medium | Good | 100M |
| HNSW | Very Fast | Hours | High | Excellent | 500M |
| DiskANN | Fast | Hours | Low | Excellent | 10B+ |
| LSH | Very Fast | Fast | Low | Medium | Unlimited |

## Key Trade-offs

**Speed vs Accuracy**: Faster indexes sacrifice some recall

**Memory vs Scale**: In-memory indexes limited by RAM

**Build Time vs Query Time**: Complex indexes take longer to build but query faster

## Choosing an Index

**For < 100K vectors**: Use Flat or HNSW

**For 100K-10M vectors**: HNSW (if memory available) or IVF

**For 10M-1B vectors**: HNSW with quantization or DiskANN

**For 1B+ vectors**: DiskANN or distributed IVF

## Advanced Techniques

**Quantization**: Compress vectors (PQ, SQ, BQ)

**Hybrid Indexes**: Combine methods (IVF-PQ, IVF-HNSW)

**Filtering**: Add metadata filtering (Filtered-DiskANN)

## Database Defaults

- **Pinecone**: Pod-based uses IVF, Serverless uses DiskANN-variant
- **Weaviate**: HNSW
- **Qdrant**: HNSW
- **Milvus**: Multiple (IVF, HNSW, DiskANN)
- **pgvector**: IVFFlat or HNSW
- **pgvectorscale**: StreamingDiskANN