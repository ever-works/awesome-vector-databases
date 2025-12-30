# pgvector-ocaml

**Category:** SDKs & Libraries  
**Tags:** sdk, pgvector, vector-store

## Overview
pgvector-ocaml provides OCaml examples for using the pgvector PostgreSQL extension, demonstrating how to perform vector indexing and nearest-neighbor search from OCaml code. It is designed to work with the `PostgreSQL-OCaml` database library.

- **Language:** OCaml  
- **Works with:** [pgvector](https://github.com/pgvector/pgvector), [PostgreSQL-OCaml](https://github.com/mmottl/postgresql-ocaml)  
- **Source:** https://github.com/pgvector/pgvector-ocaml

## Features
- Example OCaml code for integrating pgvector with PostgreSQL.
- Demonstrates how to enable the `pgvector` extension in PostgreSQL from OCaml flows.
- Shows how to create tables that store vector data.
- Examples for inserting vector values into PostgreSQL using OCaml.
- Query patterns for retrieving nearest neighbors using pgvector.
- Demonstrates adding an approximate index for faster similarity search.
- Usage of specific pgvector operator classes:
  - `vector_ip_ops` for inner product similarity.
  - `vector_cosine_ops` for cosine distance similarity.
- Includes a full working example in `example.ml`.
- Configured with Dune (`dune`, `dune-project`) for building OCaml code.
- GitHub Actions workflow for automated builds (build status badge provided).

## Technical Details
- **Ecosystem:** PostgreSQL, pgvector extension, OCaml
- **Primary use case:** Vector similarity search and indexing from OCaml applications using PostgreSQL.

## Licensing
- License file: `LICENSE.txt` (see repository for exact terms).

## Pricing
- Not applicable. This is an open-source library/example repository; no pricing information is provided.