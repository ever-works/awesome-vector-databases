## Overview

libSQL is an open source, open contribution fork of SQLite, created and maintained by Turso. It's production-ready, fully backwards compatible with SQLite, and adds features like native vector search capabilities.

## Vector Search Features

- **DiskANN Algorithm**: Implements Approximate Nearest Neighbors (ANN) using the DiskANN algorithm for efficient vector indexing
- **LM-DiskANN Variant**: Uses the LM-DiskANN algorithm optimized for scenarios where the dataset is too large to fit in memory
- **Native Integration**: Vector indexing is built directly into the database, eliminating the need for separate vector databases

## How to Use

Creating a vector index:
```sql
CREATE INDEX movies_idx ON movies (libsql_vector_idx(embedding));
```

Searching with the vector_top_k virtual table:
```sql
SELECT * FROM vector_top_k('movies_idx', query_vector, k);
```

## Performance Characteristics

While slower than in-memory approaches due to disk access latency, the FreshDiskANN implementation minimizes these delays as much as possible. It's particularly well-suited for:
- Edge computing environments
- Mobile applications
- Multi-tenant architectures where memory usage must be kept low

## Use Cases

- Semantic search in SQLite applications
- Embedding storage and retrieval on edge devices
- AI applications requiring vector similarity search
- Scenarios requiring both relational and vector data in one database

## Pricing

Free and open-source.