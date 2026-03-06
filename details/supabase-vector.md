## Overview

Supabase provides an open-source toolkit for developing AI applications using Postgres and pgvector. Vectors are enabled via pgvector, a Postgres extension for storing and querying vectors at scale.

## Key Features

- **pgvector Integration**: Native vector storage and similarity search in Postgres
- **vecs Python Client**: Purpose-built Python client for vector operations
- **RAG Support**: Built for retrieval augmented generation applications
- **Managed Postgres**: Fully managed PostgreSQL with vector capabilities
- **Multiple Distance Functions**: Cosine, Euclidean, dot product
- **Open Source**: Core tools are open source and self-hostable

## vecs Python Client

Supabase provides `vecs`, a Python client for managing unstructured vector stores:
- Create and manage collections
- Query vectors efficiently
- Built specifically for pgvector
- Simplified API for common operations
- Available on GitHub: supabase/vecs

## Vector Storage

Using the vector (pgvector) extension, Supabase enables:
- Efficient embedding storage
- Multiple similarity metrics
- Optimized indexing for performance
- Dot product tends to be fastest for normalized vectors

## Scale and Performance

Real-world usage demonstrates capability:
- Stores over 1.6 million embeddings in production
- Great performance and results at scale
- Optimized for RAG applications
- Sub-second query performance

## Use Cases

- Retrieval Augmented Generation (RAG)
- Semantic search applications
- Recommendation systems
- Document similarity matching
- AI-powered search
- Chatbots with knowledge bases

## Integration

- OpenAI embeddings
- LangChain vector stores
- Custom embedding models
- Python AI frameworks
- REST API access

## Technical Capabilities

- Store and query vector embeddings at scale
- Create and maintain vector indexes
- Combine vector search with traditional SQL
- Real-time data updates
- ACID transactions

## Deployment Options

### Supabase Cloud (Managed)
- Fully managed infrastructure
- Automatic backups and updates
- Global deployment
- Usage-based pricing

### Self-Hosted
- Open source stack
- Deploy on your infrastructure
- Complete control
- Free to use

## Documentation

Active development with recently updated docs:
- Comprehensive guides
- AI/Vector tutorials
- API documentation
- Example implementations

## Pricing

Commercial managed service with generous free tier:
- **Free Tier**: Sufficient for development and small projects
- **Pro Plan**: $25/month base + usage
- **Team**: $599/month + usage
- **Enterprise**: Custom pricing

All plans include pgvector and vector capabilities. Self-hosting is free.