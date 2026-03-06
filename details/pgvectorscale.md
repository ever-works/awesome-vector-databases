## Overview

pgvectorscale is an open-source extension for PostgreSQL that complements pgvector with higher-performance embedding search and more cost-efficient storage for AI applications. Developed by Timescale, it brings production-grade vector search capabilities to PostgreSQL.

## Key Features

- **StreamingDiskANN Index**: New index type inspired by Microsoft's DiskANN algorithm for scalable vector search
- **Statistical Binary Quantization**: Advanced compression method improving on standard Binary Quantization
- **Label-based Filtered Search**: Based on Microsoft's Filtered DiskANN research for precise, efficient filtering
- **High Performance**: Works seamlessly with pgvector for enhanced performance
- **Cost Efficient**: Optimized for storage and query efficiency

## Performance Benchmarks

On 50 million Cohere embeddings (768 dimensions):
- **28x lower p95 latency** vs. Pinecone's storage optimized index
- **16x higher query throughput** at 99% recall
- **75% less cost** when self-hosted on AWS EC2

## Architecture

Built as a PostgreSQL extension using the pgrx framework, pgvectorscale integrates natively with PostgreSQL's query planner and can be used alongside pgvector.

## Compatibility

- Works with vanilla PostgreSQL (TimescaleDB not required)
- Compatible with pgvector extension
- Available on Timescale Cloud with pgai for complete AI stack

## Use Cases

- Large-scale embedding search (millions to billions of vectors)
- Cost-sensitive production deployments
- Applications requiring filtered vector search
- RAG systems with metadata filtering

## Pricing

Free and open-source under PostgreSQL license. No licensing costs for self-hosted deployments. Timescale Cloud offers managed hosting with usage-based pricing.