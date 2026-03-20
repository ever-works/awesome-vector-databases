## Overview

SQL Server 2022 and Azure SQL introduce native vector search capabilities, allowing vector similarity search within traditional relational databases.

## Features

**Vector Storage**:
- VARBINARY columns for vectors
- JSON support for metadata
- Standard SQL operations

**Search Capabilities**:
- VECTOR_DISTANCE function
- Cosine similarity
- Euclidean distance
- Approximate nearest neighbor

**Hybrid Search**:
- Combine vector and SQL queries
- Filter by metadata before similarity search
- Join vectors with relational data

## Use Cases

- Existing SQL Server applications adding AI
- Hybrid search (SQL + vector)
- Unified data platform
- Enterprise applications with SQL skills

## Benefits

- No separate vector database needed
- Leverage existing SQL infrastructure
- ACID transactions for vectors
- Familiar SQL interface
- Enterprise security and compliance

## RRF Re-Ranking

Reciprocal Rank Fusion for combining:
- Full-text search results
- Vector similarity results
- SQL query results

## Availability

SQL Server 2022, Azure SQL Database