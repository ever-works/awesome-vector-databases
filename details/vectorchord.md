## Overview

VectorChord (vchord) is a PostgreSQL extension engineered for scalable, high-performance, and cost-effective vector search. Described as the successor of pgvecto.rs, it provides significant improvements in storage efficiency and compatibility.

## Cost Efficiency

### Storage Savings
- **Store 400,000 vectors for just $1**
- **6x more vectors** compared to Pinecone's optimized storage
- **26x more vectors** than pgvector/pgvecto.rs for the same price
- Enables massive cost reduction for large-scale deployments

### Efficient Data Types

#### RaBitQ Quantization
- **RaBitQ4**: 4-bit quantization for maximum compression
- **RaBitQ8**: 8-bit quantization with <1% recall loss
- High precision maintained with minimal storage

## pgvector Compatibility

- **Fully compatible** with pgvector data types and syntax
- Drop-in replacement for existing pgvector deployments
- No application code changes required
- Seamless migration path

## Key Features

- **Optimal Defaults**: No complex parameter tuning needed
- **High Performance**: Optimized query execution
- **Low-Bit Storage**: 4-bit and 8-bit vector support
- **Disk-Friendly**: Efficient storage and retrieval
- **Scalable**: Handles large vector datasets
- **Fast**: Quick indexing and query performance

## Technical Improvements over pgvecto.rs

- Better stability and reliability
- Enhanced performance characteristics
- Improved storage efficiency
- More mature codebase
- Active development and maintenance

## Quantization Technology

### RaBitQ (Rapid Bit Quantization)
- Advanced quantization method
- Maintains high recall with reduced precision
- Significant storage savings
- Minimal accuracy trade-off

### Benefits
- Reduced memory footprint
- Lower storage costs
- Faster data transfer
- Improved cache efficiency

## Use Cases

- Cost-sensitive large-scale vector search
- Applications with millions to billions of vectors
- PostgreSQL-native AI applications
- Migration from expensive vector databases
- Resource-constrained environments

## Installation

Available via:
- PGXN (PostgreSQL Extension Network)
- Source compilation
- Pre-built binaries
- Docker images

## Performance

- Efficient query execution
- Optimized for PostgreSQL
- Fast indexing operations
- Low memory overhead

## Development Status

Actively maintained by TensorChord:
- Regular updates and improvements
- Community contributions welcome
- Production-ready
- Long-term support

## Comparison

### vs. pgvector
- 26x more cost-effective storage
- Advanced quantization options
- Fully compatible syntax
- Better performance at scale

### vs. Pinecone
- 6x more cost-effective
- No vendor lock-in
- Self-hosted control
- PostgreSQL ecosystem benefits

### vs. pgvecto.rs (predecessor)
- Improved stability
- Better performance
- More features
- Actively maintained

## Migration

Easy migration from:
- pgvector: Compatible syntax
- pgvecto.rs: Natural upgrade path
- Other vector databases: Standard PostgreSQL tools

## Community

- GitHub: tensorchord/VectorChord
- Active issue tracking
- Community support
- Regular releases

## Pricing

Free and open-source. No licensing costs. Massive cost savings on infrastructure and storage compared to commercial alternatives.