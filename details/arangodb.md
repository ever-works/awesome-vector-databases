## Overview

ArangoDB is a multi-model database written in C++ that supports graph, document, and key-value data models with integrated vector search. It uses its proprietary ArangoDB Query Language (AQL) and persists data using RocksDB. The company rebranded to arango.ai, signaling a pivot toward AI/ML positioning.

## Features

- **Data models**: Graph, Document, and Key-Value in a single engine
- **Query language**: AQL (ArangoDB Query Language) — proprietary, not based on SQL, Cypher, Gremlin, or GraphQL
- **ArangoSearch**: Integrated full-text and analytics search engine
- **Vector Search**: kNN vector similarity search via ArangoSearch analyzers with multiple distance metrics
- **Hybrid Search**: Combine BM25 text search with kNN vector queries in a single AQL statement
- **SmartGraphs**: Efficient distributed graph traversals (Enterprise Edition only)
- **Foxx microservices**: JavaScript microservice framework that runs inside the database
- **Persistence**: Disk-based storage using RocksDB
- **Written in**: C++

## Vector Search via ArangoSearch

- **Indexing**: Define vector fields in ArangoSearch views with dimension and metric configuration
- **Distance Metrics**: Cosine, L2 (Euclidean), and dot product
- **kNN Queries**: Approximate nearest neighbor search with configurable k parameter
- **Hybrid Queries**: Combine TF-IDF/BM25 text relevance scores with vector similarity in unified ranking
- **Filtering**: Pre-filter vectors using AQL conditions before kNN computation

## Hybrid Search Capabilities

- BM25 text ranking + vector similarity in a single query
- Configurable score combination and weighting
- Faceted filtering on vector search results
- Full-text search alongside graph traversals and document queries

## Strengths

- True multi-model: documents, graphs, and vectors in one database
- No need to synchronize data across separate search, graph, and document stores
- Single query language (AQL) for all data models
- Flexible hybrid search combining text and vector relevance

## Limitations

- Does not support Cypher, Gremlin, or GraphQL — only the proprietary AQL
- Community Edition capped at 100GB dataset size (BSL 1.1 license)
- Vendor lock-in risk due to proprietary query language and BSL licensing
- No MCP server support

## Licensing

- **Community Edition**: BSL 1.1 (Business Source License 1.1) — restricted to 100GB dataset size limit, no commercial redistribution
- **Enterprise Edition**: Proprietary licensing with SmartGraphs and other advanced features
- Originally Apache 2.0, the license changed to BSL 1.1 starting with version 3.12 in 2024

## Use Cases

- Hybrid search applications requiring both text and vector retrieval
- Knowledge management combining document and graph data
- Applications needing combined document and graph storage with JavaScript microservices
- Teams already invested in AQL with datasets under 100GB

## Pricing

- Community Edition: Free (BSL 1.1) with 100GB dataset limit
- Enterprise Edition: Commercial pricing (contact vendor for details)

## Note

The license change from Apache 2.0 to BSL 1.1 in 2024 introduced the 100GB cap on the free tier and restricted commercial redistribution. Users should consider this when planning long-term deployments.