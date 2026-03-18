## Overview

Quickwit is a cloud-native search engine designed specifically for observability data, providing an open-source alternative to Datadog, Elasticsearch, Loki, and Tempo. Built in Rust on the Tantivy search library, Quickwit offers petabyte-scale log management and distributed tracing capabilities.

## Key Features

### Cloud-Native Architecture
- Decouples compute from storage
- Indexes stored in object storage (S3, GCS, etc.)
- Searchers are stateless and scale independently
- Sub-second search latency on data in object storage

### Performance & Scalability
- Handles petabyte-scale data with minimal infrastructure
- Often requires just a few nodes for massive datasets
- 10x cost efficiency over alternatives like Elasticsearch or Datadog
- Fast query execution through smart indexing and distributed processing

### Observability Support
- Native support for OpenTelemetry, Jaeger, and Elasticsearch-compatible APIs
- Tailored for log management and distributed traces
- Supports both schemaless ingestion (JSON logs) and strict schemas
- Dynamic fields and automatic schema discovery

## Use Cases

- **Log Management**: High-performance log search and analytics
- **Distributed Tracing**: OpenTelemetry and Jaeger trace storage and search
- **Observability**: Centralized observability platform for monitoring and debugging
- **Cost Optimization**: Reduce observability costs while maintaining performance

## Technical Details

### Built on Tantivy
- Leverages the fast Rust search engine library for indexing and queries
- Provides full-text search capabilities optimized for time-series data
- Supports complex query patterns and aggregations

### Data Ingestion
- Supports schemaless ingestion for flexibility
- Strict schemas available for structured data
- Automatic schema discovery for JSON documents

## Recent Developments

In January 2025, Datadog acquired Quickwit to boost real-time observability capabilities. Quickwit remains open-source, continuing to aid industries with strict data regulations.

## Pricing

Open-source and free to use, with up to 10x lower costs compared to commercial alternatives like Elasticsearch or Datadog for equivalent workloads.