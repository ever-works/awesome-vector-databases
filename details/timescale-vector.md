## Overview

Timescale Vector is a cloud solution for building search, RAG, and AI agents with PostgreSQL. It empowers developers to deploy production AI applications using PostgreSQL as their vector database, storing embeddings, relational data, and time-based data in the same system.

## Features

- **PostgreSQL Foundation**: Built on battle-tested PostgreSQL
- **Three Extensions**: pgvector, pgvectorscale, and pgai working together
- **StreamingDiskANN**: High-performance index for vector search
- **Time-Series Integration**: Native time-series capabilities alongside vectors
- **Unified Storage**: Embeddings, relational, and temporal data in one database
- **ACID Transactions**: Full PostgreSQL transactional guarantees
- **SQL Interface**: Use standard SQL for all operations
- **Scalability**: Handles large-scale vector workloads

## Performance

pgvector with the pgvectorscale extension achieves 471 queries per second at 99% recall on 50 million vectors. At 99% recall, pgvectorscale shows an 11.4x QPS advantage over Qdrant.

## Components

- **pgvector**: Core vector similarity search extension
- **pgvectorscale**: StreamingDiskANN index and performance enhancements
- **pgai**: AI integration and tooling

## Use Cases

- AI applications requiring both structured and vector data
- Time-series analysis with semantic search
- Production RAG systems
- Applications already using PostgreSQL
- Enterprise systems requiring ACID guarantees

## Integration

Works with LangChain, LlamaIndex, and standard PostgreSQL tools and clients.

## Pricing

Available on Timescale Cloud with various pricing tiers. Open-source extensions also available for self-hosting.