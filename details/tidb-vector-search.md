## Overview

TiDB, a MySQL-compatible database, has introduced built-in vector search capabilities, enabling seamless storage and search for vectors directly using SQL. TiDB extends MySQL syntax to support Vector Search and introduces new Vector data types and several vector functions.

## Key Features

### MySQL Compatibility
TiDB Serverless brings built-in vector search to the MySQL landscape. Developers can leverage the familiar SQL environment to effortlessly join, index, and query both operational and vector data. This capability enables advanced semantic searches, combining the power of vector search with the reliability and ease of MySQL.

### Vector Data Types
The following Vector data types are currently available:
- **VECTOR**: A sequence of single-precision floating-point numbers with any dimension

Note: Vector data types are TiDB specific, and are not supported in standard MySQL.

### Vector Indexes
TiDB implements vector indexes using the Hierarchical Navigable Small World (HNSW) method for efficient nearest neighbor searches.

## Benefits

### Unified Data Architecture
The built-in approach eliminates the need for separate databases for vector and operational data, thus avoiding data redundancy. Store vector embeddings directly alongside your MySQL data, simplifying your data architecture with the straightforwardness of SQL.

### No External Dependencies
Everything runs within TiDB, eliminating the complexity of managing separate vector databases and keeping data synchronized.

## Platform Availability

Vector data types are available on:
- TiDB Self-Managed
- TiDB Cloud Starter
- TiDB Cloud Essential
- TiDB Cloud Dedicated

For TiDB Self-Managed and TiDB Cloud Dedicated, the TiDB version must be v8.4.0 or later (v8.5.0 or later is recommended).

## Use Cases

- Semantic search in MySQL applications
- RAG (Retrieval Augmented Generation) applications
- Recommendation systems
- AI applications requiring MySQL compatibility
- Applications needing both transactional and vector search capabilities

## Pricing

Varies by TiDB deployment option (Serverless, Dedicated, Self-Managed). Consult PingCAP pricing for details.