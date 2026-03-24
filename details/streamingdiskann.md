## Overview

StreamingDiskANN is a custom index type in pgvectorscale inspired by Microsoft's DiskANN algorithm, optimized for disk-based storage with efficient streaming updates.

## Key Features

- Disk-based index supporting billions of vectors
- Streaming updates without full rebuilds
- SSD-optimized for sequential I/O
- Memory-efficient with configurable cache
- PostgreSQL-native implementation

## Architecture

The index uses:
- Graph-based ANN structure (HNSW-like)
- Disk layout optimized for SSDs
- Incremental updates via streaming
- LRU cache for hot data
- Background compaction

## Performance

On 50 million Cohere embeddings:
- 471 QPS at 99% recall
- 28x lower p95 latency vs Pinecone
- 16x higher throughput vs Qdrant
- 75% lower cost when self-hosted

## Comparison to Alternatives

- **In-memory HNSW**: Faster but memory-limited
- **Traditional DiskANN**: Requires full rebuilds
- **StreamingDiskANN**: Best of both worlds

## Integration

Seamlessly integrates with PostgreSQL:
- Standard SQL syntax
- Transaction support
- pg vector compatibility
- Familiar tooling

## Pricing

Open-source as part of pgvectorscale.