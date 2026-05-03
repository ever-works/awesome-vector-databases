## Overview

pgvectorscale supercharges pgvector with DiskANN for massive-scale vector search in Postgres.

## Features

- **StreamingDiskANN**: Disk-based, high-recall index
- **Hybrid Search**: SQL filters + vector ANN
- **Optimizations**: Binary quant, filtered search
- **Performance**: 16x throughput, 75% cost savings vs Pinecone

## Use Cases

- **Enterprise RAG**: Billion-vector retrieval
- **Analytics**: Large-scale embedding ops
- **Production Search**: Low-latency, high QPS

## Comparisons

**vs Dedicated DBs (Weaviate/Pinecone)**: Unified Postgres stack, no ETL/sync, ACID txns, mature ecosystem.
**vs pgvector**: Dramatically better scale/latency.

## Pricing

Free open-source (Timescale License).