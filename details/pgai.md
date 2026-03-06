## Overview

pgai is a suite of tools that transforms PostgreSQL into a robust, production-ready retrieval engine for RAG and Agentic AI applications. It automatically creates and synchronizes vector embeddings from PostgreSQL data and S3 documents.

## Key Features

- **pgai Vectorizer**: Declarative approach to embedding generation that treats embeddings like database indexes
- **Automatic Synchronization**: Keeps embeddings in sync as data changes
- **Batch Processing**: Efficient embedding generation with built-in handling for failures, rate limits, and latency spikes
- **Multi-Model Support**: Works with OpenAI, Cohere, and other embedding providers
- **S3 Integration**: Direct embedding of documents stored in S3
- **Reliability**: Handles model failures and unreliable endpoints gracefully

## Components

pgai works as part of a three-extension stack on Timescale Cloud:
1. **pgvector**: Provides vector data type and HNSW index
2. **pgvectorscale**: StreamingDiskANN index for performance
3. **pgai**: Embedding generation and AI model integration

## Supported Models

- OpenAI: text-embedding-ada-002 and other embedding models
- Cohere: Multiple representation models for English and multilingual text
- Extensible to other providers

## Use Cases

- RAG (Retrieval Augmented Generation) applications
- Semantic search over PostgreSQL data
- Automated embedding pipelines
- AI-powered data applications

## Installation

Available via:
- PyPI: `pip install pgai`
- PostgreSQL extension installation
- Pre-configured on Timescale Cloud

## Pricing

Free and open-source. Available on GitHub at github.com/timescale/pgai under Apache 2.0 license. Timescale Cloud provides managed hosting with usage-based pricing.