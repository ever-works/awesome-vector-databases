# PGVector

[PGVector](https://github.com/pgvector/pgvector) is an open-source PostgreSQL extension that enables efficient storage, indexing, and similarity search for vector embeddings directly within a Postgres database. It supports both exact and approximate nearest neighbor search, and a variety of vector types and distance metrics.

## Features

- **Vector Storage**: Store vectors alongside other data in Postgres tables.
  - Supports single-precision, half-precision (halfvec), binary (bit), and sparse (sparsevec) vectors.
  - Can store vectors with up to 16,000 dimensions (vector), 4,000 (halfvec), 64,000 (bit), or 1,000 non-zero elements (sparsevec).
- **Similarity Search**:
  - Exact and approximate nearest neighbor search.
  - Multiple distance metrics: L2 (Euclidean), inner product, cosine, L1 (taxicab), Hamming (for binary), and Jaccard (for binary).
- **Indexing**:
  - Exact search by default.
  - Approximate search via HNSW and IVFFlat indexes for faster queries at the cost of some recall.
  - Index tuning options for memory, parallelism, and recall/speed tradeoffs.
  - Support for filtering and iterative index scans to improve recall when filtering.
- **Querying**:
  - Retrieve nearest neighbors to a vector or another row.
  - Query by distance threshold.
  - Aggregate functions: average, sum of vectors.
  - Subvector indexing and querying.
- **Hybrid Search**:
  - Combine with Postgres full-text search for hybrid queries.
- **Language Support**:
  - Usable from any language with a Postgres client.
  - Libraries/examples available for C, C++, C#, Go, Java, JavaScript/TypeScript, Python, Ruby, Rust, and more.
- **Postgres Integration**:
  - ACID compliance, point-in-time recovery, JOINs, and all standard Postgres features.
  - Supports replication through WAL.
  - Scalable with standard Postgres scaling techniques (vertical and horizontal).
- **Performance and Tuning**:
  - Bulk loading with COPY.
  - Index build and query performance tuning.
  - Monitoring with `pg_stat_statements`.
  - Options for concurrent index creation, parallelism, and memory usage.
- **Installation**:
  - Available via compiling from source, Docker, Homebrew, PGXN, APT, Yum, pkg, conda-forge, and preinstalled on some hosted Postgres providers.
  - Works on Linux, macOS, and Windows.
- **Data Flexibility**:
  - Store vectors with different dimensions using untyped columns (with some limitations on indexing).
  - Support for higher-precision vectors using Postgres array types.
- **Functions and Operators**:
  - Rich set of operators for vector arithmetic and similarity.
  - Functions for distance calculation, normalization, quantization, and more.
- **Open Source**:
  - Licensed under an open-source license, available for community contributions.

## Pricing

PGVector is open-source and free to use.

## Links

- [Source code and documentation](https://github.com/pgvector/pgvector)