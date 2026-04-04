## Overview

ArcadeDB is a multi-model database engine written in Java that supports graph, document, key-value, time-series, vector, and full-text search data models in a single engine. It is a Neo4j alternative offering compatibility with Cypher queries (97.8% TCK compliance) and the BOLT protocol, with a built-in Neo4j importer for migration.

## Features

- **Multi-model engine**: Graph, Document, Key-Value, Time-Series, Vector, and Search in one engine without data duplication or ETL pipelines
- **Query languages**: SQL, Cypher (OpenCypher standard), Gremlin, GraphQL, and MongoDB-compatible MQL
- **Licensing**: Apache 2.0 — fully open-source with no data caps, no commercial restrictions, and no license conversion terms
- **AI/Agent readiness**: Built-in MCP (Model Context Protocol) server for direct LLM-to-database communication
- **Vector search**: Native vector search with no plugins or separate infrastructure required
- **Persistence**: Disk-based storage with in-memory caching
- **BOLT protocol support**: Neo4j driver compatibility
- **Neo4j importer**: Built-in tool to read Neo4j export files directly
- **Graph OLAP Engine**: Native graph analytics with top LDBC Graphalytics benchmark performance (PageRank: 0.48s, WCC: 0.30s, BFS: 0.13s)

## Performance

In LDBC Graphalytics benchmarks, ArcadeDB leads on every algorithm both in embedded mode and as a Docker container:

- PageRank: 0.48s (embedded), 0.83s (Docker)
- WCC: 0.30s (embedded), 0.22s (Docker)
- BFS: 0.13s (embedded), 0.07s (Docker)
- SSSP: 3.53s (embedded), 0.97s (Docker)
- CDLP: 3.67s (embedded), 3.35s (Docker)
- LCC: 27.41s (embedded), 34.98s (Docker)

## Use Cases

- Teams migrating from Neo4j seeking Cypher compatibility without vendor lock-in
- Applications requiring multiple data models without separate databases
- AI/LLM applications needing native vector search and MCP integration
- High-throughput ingestion workloads (2M+ records/second on commodity hardware)

## Pricing

Free and open-source under the Apache 2.0 license with no data caps, no commercial restrictions, and no paid enterprise tier. The software is free to use, embed, modify, and distribute.