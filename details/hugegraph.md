## Overview

HugeGraph is a distributed graph database managed as an Apache Software Foundation top-level project, originally developed at Baidu. It supports pluggable storage backends (RocksDB, HBase, Cassandra, MySQL, ScyllaDB) and can scale horizontally for very large graphs. The project uses Apache 2.0 licensing with genuine open-source governance.

## Features

- **Architecture**: Separate OLTP and OLAP engines for clean separation of concerns
  - **HugeGraph Server**: OLTP engine written in Java for real-time graph operations
  - **Vermeer**: Go-based OLAP compute engine for graph analytics at scale
- **Query languages**: Gremlin (Apache TinkerPop) and RESTful API
- **Data model**: Property graph (single model)
- **Storage backends**: Pluggable — RocksDB, HBase, Cassandra, MySQL, ScyllaDB
- **Scaling**: Horizontal scaling for billion-scale graphs
- **Persistence**: Disk-based via configured backend
- **Graph algorithms**: PageRank, WCC, BFS, LCC, Label Propagation (CDLP), unweighted SSSP
- **Vector Search**: HNSW and DiskANN indexes for vector similarity search at billion-scale
- **Licensing**: Apache 2.0 — OSI-approved open source, governed by Apache Software Foundation

## Vector Search Capabilities

- **HNSW Index**: Hierarchical Navigable Small World graph index for approximate nearest neighbor search
- **DiskANN Index**: Disk-based approximate nearest neighbor index for memory-efficient billion-scale vector search
- **Integrated with Graph**: Vector search runs alongside graph queries within the same platform
- **Use Cases**: Fraud detection at scale, billion-node knowledge graphs with semantic similarity

## Strengths

- Genuine open-source governance through Apache foundation — not a single-vendor project
- Strong adoption in China, particularly at Baidu and other major tech companies
- Pluggable storage allows tuning backend for specific scalability needs
- Free to use with no data caps or commercial restrictions
- Billion-scale graph + vector workload support

## Limitations

- **No Cypher support**: Uses only Gremlin and REST API — no Cypher, SQL, or GraphQL
- **No weighted shortest paths**: Vermeer's SSSP computes only unweighted shortest paths (hop count) — no weighted Dijkstra variant
- **Performance trails competitors**: In LDBC Graphalytics benchmarks, significantly slower than alternatives (e.g., PageRank 4.8x slower than ArcadeDB in Docker-to-Docker comparison; CDLP 18.7x slower)
- **Complex deployment**: Requires multiple components — server, Vermeer master + worker containers, storage backend
- **Smaller ecosystem**: English documentation exists but is less comprehensive; much community content is in Chinese

## Use Cases

- Very large-scale graph deployments requiring Apache-licensed governance
- Billion-scale fraud detection with combined graph structure and vector similarity
- Knowledge graphs with semantic search at scale
- Teams comfortable with Gremlin query language
- Organizations needing pluggable storage architecture for specific scalability requirements

## Pricing

Free and open-source under the Apache 2.0 license with no data caps or commercial restrictions. No paid enterprise tier.