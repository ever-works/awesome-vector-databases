---
title: pgvector-pascal
slug: pgvector-pascal
brand: pgvector
category: sdks-libraries
tags:
  - sdk
  - pgvector
  - vector-store
source_url: https://github.com/pgvector/pgvector-pascal
images:
  - https://opengraph.githubassets.com/1/pgvector/pgvector-pascal
---

## Overview

pgvector-pascal provides Pascal examples and bindings for using the pgvector PostgreSQL extension, enabling vector similarity search from Pascal applications. It currently supports the SQLDB database library from Free Pascal.

## Features

- **Pascal bindings for pgvector**  
  - Demonstrates how to use PostgreSQL’s `vector` type from Pascal code
  - Integrates with the pgvector extension for vector similarity search

- **SQLDB support**  
  - Works with Free Pascal’s [SQLDB](https://www.freepascal.org/docs-html/fcl/sqldb/) library
  - Uses `TSQLQuery` (or equivalent) to execute SQL with vector types and parameters

- **Extension setup**  
  - Example code to enable the pgvector extension:  
    `CREATE EXTENSION IF NOT EXISTS vector`  
  - Shows how to run this via `Query.SQL.Text` and `Query.ExecSQL`

- **Schema definition with vector columns**  
  - Example table creation with a vector column:  
    `CREATE TABLE items (id bigserial PRIMARY KEY, embedding vector(3))`

- **Inserting vectors from Pascal**  
  - Parameterized insert statements using Pascal string parameters cast to `vector` type  
  - Demonstrates inserting multiple vector rows in one statement:  
    `INSERT INTO items (embedding) VALUES ((:embedding1)::vector), ((:embedding2)::vector)`

- **Nearest neighbor search**  
  - Example query ordering by vector distance:  
    `SELECT * FROM items ORDER BY embedding <-> (:embedding)::vector LIMIT 5`  
  - Shows how to bind query parameters and iterate over result rows in Pascal

- **Approximate vector indexing**  
  - Examples of creating HNSW index:  
    `CREATE INDEX ON items USING hnsw (embedding vector_l2_ops)`  
  - Examples of creating IVFFlat index with configuration:  
    `CREATE INDEX ON items USING ivfflat (embedding vector_l2_ops) WITH (lists = 100)`

- **Multiple distance metrics**  
  - Notes on choosing operator classes for different similarity metrics:  
    - `vector_l2_ops` for Euclidean (L2) distance  
    - `vector_ip_ops` for inner product  
    - `vector_cosine_ops` for cosine distance

- **Runnable example program**  
  - Repository includes a complete example (`example.pp`) showing end-to-end usage:  
    extension creation, table creation, inserts, search, and iteration over results

- **Development and testing setup**  
  - Example commands to clone and run:  
    - `git clone https://github.com/pgvector/pgvector-pascal.git`  
    - `cd pgvector-pascal`  
    - `createdb pgvector_pascal_test`  
    - `fpc example.pp` and `./example`  
  - Instructions for specifying the path to `libpq` by symlinking `libpq.dylib` when needed

## Usage

- Install and enable pgvector in PostgreSQL.
- Use SQLDB in a Free Pascal application to:
  - Enable the extension (`CREATE EXTENSION IF NOT EXISTS vector`).
  - Create tables with `vector(n)` columns.
  - Insert vectors as strings cast to `vector` type via parameters.
  - Run similarity queries with `<->` and limit results.
  - Add HNSW or IVFFlat indexes for approximate nearest neighbor search.

## Pricing

- Not specified in the provided content (GitHub-hosted example/binding, typically open source).
