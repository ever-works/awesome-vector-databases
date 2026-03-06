## Overview

Neon is Serverless Postgres built for the cloud with native support for pgvector extension, enabling efficient vector storage and semantic search. Architecture separates compute from storage for serverless features.

## Key Features

- **Serverless Architecture**: Separate compute and storage layers
- **Instant Provisioning**: Databases ready in seconds
- **Autoscaling**: Automatic scaling based on demand
- **Scale to Zero**: Automatic pause when idle to reduce costs
- **pgvector Support**: Native vector similarity search in PostgreSQL
- **Branch-Based Development**: Git-like branching for databases

## Vector Search Capabilities

- Full pgvector extension support
- Store embeddings alongside regular data
- Vector similarity search with SQL queries
- Compatible with OpenAI and other embedding providers
- Elasticsearch-grade vector features in Postgres

## Serverless Features

- **Instant Provisioning**: No waiting for database setup
- **Autoscaling**: Compute scales automatically with load
- **Scale to Zero**: No charges when database is idle
- **Branching**: Create instant database copies for development
- **Time Travel**: Point-in-time recovery

## Integration

### Semantic Kernel
- Official Neon Serverless Postgres Connector
- Powers RAG workflows
- Enables intelligent AI applications

### LangChain
- Native Neon Postgres integration
- Vector store for LangChain applications
- Seamless embedding storage and retrieval

### OpenAI
- Direct integration with OpenAI embeddings
- Examples in OpenAI Cookbook
- Optimized for GPT-powered applications

## Use Cases

- RAG (Retrieval Augmented Generation) systems
- Semantic search applications
- AI-powered search with natural language
- LLM applications requiring vector memory
- Multi-modal search combining vectors and structured data

## Enabling pgvector

```sql
CREATE EXTENSION vector;
```

Available in Neon SQL Editor or via any PostgreSQL client.

## Architecture Benefits

- **Separated Storage**: Durable, scalable storage independent of compute
- **Elastic Compute**: Scale compute resources independently
- **Efficient Costs**: Pay only for actual usage
- **High Availability**: Built-in redundancy and failover

## Pricing

Commercial managed service with free tier:
- **Free Tier**: Generous limits for development and small projects
- **Pro Plan**: Usage-based pricing for production workloads
- **Enterprise**: Custom pricing with SLA and dedicated support

Detailed pricing available at: neon.com/pricing

## Resources

- Jupyter notebooks for vector search with OpenAI
- Comprehensive guides for building intelligent search
- Active community and documentation