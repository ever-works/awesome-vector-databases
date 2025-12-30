# pgvector-erlang

**Category:** SDKs & Libraries  
**Brand:** pgvector  
**Repository:** https://github.com/pgvector/pgvector-erlang

Erlang client examples for the pgvector PostgreSQL extension, demonstrating how to run vector operations from Erlang systems using `epgsql`.

---

## Features

- **Erlang examples for pgvector**
  - Shows how to integrate the pgvector extension with Erlang applications.
  - Focused around the `epgsql` PostgreSQL driver.

- **epgsql support**
  - Uses `epgsql:equery/3` for executing SQL commands from Erlang.
  - Compatible with databases where the pgvector extension is installed.

- **Extension setup**
  - Example for enabling the pgvector extension:
    - `CREATE EXTENSION IF NOT EXISTS vector`

- **Schema definition for vector data**
  - Example of creating a table with vector columns:
    - `CREATE TABLE items (id bigserial PRIMARY KEY, embedding vector(3))`

- **Vector insertion**
  - Demonstrates inserting vector data into PostgreSQL from Erlang:
    - `INSERT INTO items (embedding) VALUES ($1), ($2)` with vector values like `[1,2,3]`.

- **Nearest neighbor queries**
  - Example query to retrieve nearest neighbors by distance:
    - `SELECT id FROM items ORDER BY embedding <-> $1 LIMIT 5`
  - Uses the `<->` operator for distance-based ordering.

- **Approximate nearest neighbor indexing**
  - Examples of creating approximate indexes for faster search:
    - HNSW index: `CREATE INDEX ON items USING hnsw (embedding vector_l2_ops)`
    - IVFFlat index: `CREATE INDEX ON items USING ivfflat (embedding vector_l2_ops) WITH (lists = 100)`

- **Multiple distance metrics**
  - Support for different operator classes via configuration in SQL:
    - `vector_l2_ops` – L2 (Euclidean) distance
    - `vector_ip_ops` – inner product
    - `vector_cosine_ops` – cosine distance

- **Example project setup for development**
  - Steps shown in the repo for running the example:
    - Clone repository
    - Create test database `pgvector_erlang_test`
    - Build with `rebar3 escriptize`
    - Run example script from `_build/default/bin/example`
  - Full example available in `src/example.erl`.

---

## Integration

- **Primary driver:** `epgsql` (Erlang PostgreSQL driver)
- **Database:** PostgreSQL with `pgvector` extension enabled

---

## Pricing

- Not specified in the provided content. The project appears to be an open-source library hosted on GitHub.