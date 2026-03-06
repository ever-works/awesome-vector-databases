## Overview

Rockset was a real-time analytics database built for the cloud with native vector search capabilities. Acquired by OpenAI in 2024 to power retrieval infrastructure across OpenAI's products, demonstrating its production-grade vector search capabilities.

## Key Features (Historical)

### Vector Search
- Native vector embedding support
- Similarity search indexes
- Hybrid search combining vectors with filtering and aggregations
- Billions of vectors at scale
- Thousands of queries per second

### Real-Time Analytics
- Sub-second ingest latency
- Millisecond query latency (P50: 10ms on customer workloads)
- 20,000+ QPS sustained performance
- Immediate data availability in searches

### Converged Index
- Unified index combining:
  - Search index
  - Columnar store
  - Row store
  - Similarity index (vector)
- Scales to billions of vectors and terabytes of data

## Technical Architecture

- Built on top of RocksDB
- FAISS Inverted File Indexes for ANN
- Distributed architecture for scale
- Real-time data ingestion
- Cloud-native design

## Performance Characteristics

- **Ingest Latency**: Sub-second
- **Query Latency**: Milliseconds (P50: 10ms)
- **Throughput**: 20,000+ QPS
- **Scale**: Billions of vectors
- **Data Freshness**: Real-time visibility

## Use Cases (Historical)

- Real-time vector search at scale
- Hybrid search with filtering
- High-throughput production applications
- Machine learning applications
- Personalization engines
- Real-time recommendations

## Hybrid Search Capabilities

Rockset excelled at combining:
- Vector similarity search
- SQL filtering and aggregations
- Real-time analytics
- Complex joins and transformations

This enabled sophisticated search experiences beyond pure vector similarity.

## OpenAI Acquisition (2024)

OpenAI acquired Rockset to:
- Power retrieval infrastructure across products
- Leverage world-class data indexing and querying
- Enhance vector search capabilities
- Support production-scale AI applications

The acquisition validates Rockset's technology as production-ready for demanding AI workloads.

## Historical Pricing

Commercial service with usage-based pricing. Specific pricing details are no longer publicly available following the OpenAI acquisition.

## Current Status

Following the OpenAI acquisition:
- Technology integrated into OpenAI infrastructure
- Public service availability has changed
- Contact OpenAI for information about retrieval capabilities

## Legacy and Impact

- Demonstrated viability of converged analytics + vector search
- Proved real-time vector search at scale
- Influenced subsequent vector database architectures
- Validated hybrid search approach

## Technical Resources

Historical technical blog posts and documentation showcase:
- Converged index architecture
- Billion-scale vector search implementation
- Real-time ingest and query optimization
- Production deployment best practices