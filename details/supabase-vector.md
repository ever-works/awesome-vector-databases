## Overview

Supabase provides an open-source toolkit for developing AI applications using Postgres and pgvector. Vectors are enabled via pgvector, a Postgres extension for storing and querying vectors at scale.

## Key Features

- **pgvector Integration**: Native vector storage and similarity search in Postgres
- **vecs Python Client**: Purpose-built for vector operations
- **Serverless Scaling**: Auto-scaling compute
- **Real-time Subscriptions**: Live query updates
- **Row Level Security (RLS)**: Multi-tenant support
- **Edge Functions**: Serverless JS/TS compute
- **Auto-indexing**: HNSW indexes

## Use Cases

- Multi-tenant AI apps with auth and realtime
- Full-stack RAG applications
- Semantic search with SQL filtering
- Chatbots and recommendation systems

## Comparisons

**vs Dedicated Vector DBs:**

| Aspect | Supabase + pgvector | Dedicated Vector DBs |
|--------|---------------------|----------------------|
| SQL Power | Full Postgres | Limited |
| Realtime | Native subs | Add-ons/polling |
| Multi-Tenant | RLS built-in | Custom impl |
| Full-Stack | Auth/storage incl. | DB only |

## Pricing

- **Free Tier**: Generous for dev
- **Pro**: $25/month + usage
- **Team/Enterprise**: Higher tiers
Self-hosting free.