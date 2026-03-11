## Overview

pgvectorscale is an open-source PostgreSQL extension that extends pgvector with advanced indexing and optimization techniques for AI applications. It delivers higher-performance embedding search and more cost-efficient storage.

## Key Innovations

### StreamingDiskANN Index

Based on Microsoft Research's DiskANN algorithm:
- **Disk-Based**: Handles datasets larger than RAM
- **Streaming Updates**: Incremental index updates without full rebuilds
- **High Performance**: Optimized for SSD storage
- **Scalability**: Billions of vectors support

### Statistical Binary Quantization

Developed by Timescale researchers:
- **Compression**: Reduce storage footprint significantly
- **Speed**: Faster similarity computations
- **Accuracy**: Minimal recall degradation
- **Cost Savings**: Lower storage and compute costs

### Filtered Vector Search

Based on Microsoft's Filtered DiskANN research:
- **Label-Based Filtering**: Combine vector search with metadata filters
- **Efficient**: No separate pre-filtering step
- **Flexible**: Complex filter combinations supported

## Performance Benchmarks

### vs Pinecone (50M Cohere embeddings, 768 dimensions)

- **28x Lower p95 Latency**: Faster response times
- **16x Higher Query Throughput**: More queries per second
- **75% Lower Cost**: When self-hosted on AWS EC2
- **99% Recall**: Maintained accuracy level

Benchmark against Pinecone's storage-optimized (s1) index.

## Compatibility

- **PostgreSQL**: Works with vanilla PostgreSQL (no TimescaleDB required)
- **pgvector**: Builds on top of pgvector (auto-installs as dependency)
- **Cloud & On-Premise**: Deploy anywhere PostgreSQL runs

## Installation

### CASCADE Install

Automatically installs pgvector when installing pgvectorscale:

```sql
CREATE EXTENSION vectorscale CASCADE;
```

### Deployment Options

- **Timescale Cloud**: Fully managed with pgai suite (pgvector + pgvectorscale + pgai)
- **Docker**: TimescaleDB Docker images include pgvectorscale
- **Self-Hosted**: Compile from source on any PostgreSQL
- **Cloud Platforms**: Available on major PostgreSQL cloud providers

## Integration with pgai Suite

Timescale's pgai suite combines three extensions:

1. **pgvector**: Core vector operations
2. **pgvectorscale**: Performance optimization
3. **pgai**: AI model integration and workflows

## Key Features

- **ACID Transactions**: Full PostgreSQL transactional guarantees
- **SQL Interface**: Standard SQL for vector operations
- **Concurrent Updates**: Safe multi-user concurrent access
- **Backup & Recovery**: Standard PostgreSQL tools work
- **Replication**: Use PostgreSQL streaming replication

## Use Cases

- **Large-Scale RAG**: Retrieval-augmented generation at scale
- **Semantic Search**: High-performance similarity search
- **Recommendation Systems**: Vector-based recommendations
- **Document Retrieval**: Large document collections
- **Enterprise AI**: Cost-effective alternative to managed services

## Advantages

### vs Specialized Vector Databases

- **Unified Platform**: Vector + relational data in one database
- **Cost Efficiency**: 75% cost savings vs managed services
- **Operational Simplicity**: Leverage existing PostgreSQL expertise
- **Data Locality**: No separate vector database to synchronize
- **Open Source**: Full transparency and control

### vs pgvector Alone

- **Better Performance**: Optimized indexing algorithms
- **Larger Scale**: Handle datasets exceeding RAM
- **Lower Costs**: Storage and compute optimizations
- **Advanced Features**: Filtering, quantization, streaming updates

## Technical Specifications

- **Index Type**: StreamingDiskANN (graph-based)
- **Quantization**: Statistical binary quantization
- **Storage**: SSD-optimized disk-based indexing
- **Updates**: Streaming incremental updates
- **Filtering**: Native filtered search support

## Benchmarking

Publicly documented benchmarks show:
- Outperforms Pinecone on cost and performance
- Competitive with specialized vector databases
- Scales to 50M+ vectors efficiently
- Maintains high recall (99%+)

## Licensing

Open-source under PostgreSQL license:
- Free for commercial use
- No vendor lock-in
- Community-driven development
- Enterprise support available through Timescale

## Pricing

### Open Source
Free and open-source for self-hosting

### Timescale Cloud
Managed PostgreSQL with pgvectorscale:
- Usage-based pricing
- Fully managed operations
- Automatic scaling
- Enterprise support included