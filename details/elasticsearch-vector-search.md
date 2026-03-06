## Overview

Elasticsearch provides robust k-nearest neighbor (kNN) search capabilities for finding semantically similar vectors using cosine or L2 norm metrics. Retrieve results based on semantic meaning rather than exact keyword matches.

## kNN Search Methods

### Approximate kNN (Recommended)
- Uses knn option, knn query, or knn retriever
- Ideal for production workloads
- HNSW algorithm for efficiency
- Scales to millions of vectors

### Exact Brute-Force kNN
- Uses script_score query with vector function
- Best for small datasets (<10K documents)
- Precise scoring
- Higher computational cost

## Recent Enhancements (2026)

### Performance Improvements
- **Adaptive Early Termination**: New HNSW strategy (March 2, 2026)
- **bfloat16 Support**: Halves vector data storage (February 16, 2026)
- **Improved Concurrency**: Better kNN graph traversal
- **Advanced Quantization**: 8-bit and 4-bit options to reduce memory

### Filtered Vector Search
- Sub-50ms kNN queries with term/range filters
- Efficient handling of millions of vector documents
- Integrated filtering without separate indices

## Key Features

- **Dense Vector Field**: dense_vector field type for embeddings
- **Multiple Similarity Metrics**: Cosine, dot product, L2 norm
- **Hybrid Search**: Combine vector and text search
- **Quantization**: 8-bit, 4-bit, and bfloat16 for efficiency
- **Native Match Support**: knn with traditional queries
- **Sparse Vector**: Support for sparse embeddings

## Technical Capabilities

### Indexing
- HNSW (Hierarchical Navigable Small World)
- Configurable graph parameters
- Optimized for query performance
- Dynamic index updates

### Query Performance
- Sub-50ms with filters
- Scales to millions of documents
- Concurrent query execution
- Optimized resource usage

## Use Cases

- Semantic search applications
- Recommendation engines
- Content discovery
- Image similarity search
- Question answering systems
- Fraud detection

## Setup Requirements

1. **Data Vectorization**: Use NLP models in Elasticsearch or external embedding services
2. **Field Type**: Configure dense_vector fields in index mappings
3. **Index Settings**: Optimize HNSW parameters for your use case
4. **Query Configuration**: Choose approximate or exact kNN based on needs

## Integration

- LangChain vector store
- LlamaIndex integration
- Native language clients (Python, Java, JavaScript, etc.)
- REST API access
- Kibana for visualization

## Elastic Cloud

Managed Elasticsearch with vector search:
- Automatic scaling
- Security and monitoring
- Multi-cloud deployment (AWS, Azure, GCP)
- Enterprise features

## Benchmarks

Recent comparisons:
- Filtered vector search vs. OpenSearch (February 25, 2026)
- Performance with different quantization levels
- Latency under various load conditions

## Pricing

### Open Source (Elasticsearch OSS)
Free for basic features under Apache 2.0 or SSPL license.

### Elastic License
Commercial features including:
- Advanced security
- Machine learning
- Alert capabilities
- Enterprise support

### Elastic Cloud (Managed)
Usage-based pricing:
- **Standard**: Starting at $95/month
- **Gold**: $125/month
- **Platinum**: $175/month
- **Enterprise**: Custom pricing

All tiers include vector search capabilities. 14-day free trial available.

## Documentation

Extensive resources:
- Elasticsearch Labs tutorials
- Vector search implementation guides
- API documentation
- Performance tuning guides