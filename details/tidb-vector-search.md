## Overview

TiDB, a MySQL-compatible database, has introduced built-in vector search capabilities, enabling seamless storage and search for vectors directly using SQL. TiDB extends MySQL syntax to support Vector Search and introduces new Vector data types and several vector functions.

## Key Features

### MySQL Compatibility
TiDB Serverless brings built-in vector search to the MySQL landscape. Developers can leverage the familiar SQL environment to effortlessly join, index, and query both operational and vector data.

### Vector Data Types
- **VECTOR**: A sequence of single-precision floating-point numbers with any dimension

### Vector Indexes
TiDB implements vector indexes using the Hierarchical Navigable Small World (HNSW) method.

## Benefits

### Unified Data Architecture
Eliminates need for separate databases; ACID transactions on hybrid data.

## Use Cases

- Semantic search in MySQL apps
- RAG applications
- Existing SQL infra upgrades

## Comparisons

No data sync issues vs dedicated VDBs.

## Pricing

Varies by deployment; consult PingCAP.