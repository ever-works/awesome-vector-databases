## Overview

Neon is a serverless PostgreSQL platform that combines traditional database capabilities with modern cloud-native features, offering native pgvector support for AI and vector search applications.

## Key Features

### Serverless Architecture
- **Compute-Storage Separation**: Independent scaling of compute and storage
- **Instant Provisioning**: Database creation in under 1 second
- **Auto-Scaling**: Automatic compute scaling based on demand
- **Scale to Zero**: Databases automatically pause when idle
- **Pay-per-Use**: Only pay for active compute time

### pgvector Support
- Native pgvector extension support
- HNSW indexing for fast similarity search
- IVFFlat indexes available
- Full PostgreSQL 15+ compatibility
- Embedding dimensions up to 2000

### Branching
- Database branching similar to Git
- Instant branch creation from any point in time
- Perfect for development/staging workflows
- Zero-cost copies for testing

### Security & Multi-Tenancy
- Row Level Security (RLS)
- SOC 2 compliant
- Point-in-time recovery

## Use Cases
- Multi-tenant AI apps (RAG, semantic search)
- Serverless AI inference pipelines
- Global development teams with branching

## Comparisons

**vs Dedicated Vector DBs:** Full Postgres SQL (joins, analytics, ACID) + vectors vs specialized but limited querying.

| Feature | Neon + pgvector | Dedicated (e.g., Pinecone, Weaviate) |
|---------|-----------------|-------------------------------------|
| Serverless Scaling | Instant, scale-to-zero | Usage-based |
| SQL + Vectors | Native hybrid | Often separate |
| Branching | Git-like | None |
| Cost for Idle | $0 | Minimums |

## Pricing

### Free Tier
- 512 MB storage
- 0.5 compute hours/month
- Unlimited projects

### Paid Plans
- **Launch**: $19/month base + usage
- **Scale**: Custom
- **Enterprise**: Volume discounts

Compute per active hour, storage per GB-month.