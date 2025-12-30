# pgvector-perl

Perl client and examples for using the `pgvector` PostgreSQL extension, enabling vector data types and similarity queries from Perl applications.

- **Category:** SDKs & Libraries  
- **Language:** Perl  
- **Ecosystem:** PostgreSQL, pgvector  
- **License:** MIT  
- **Source:** https://github.com/pgvector/pgvector-perl

## Overview

`pgvector-perl` provides example code and patterns for integrating the `pgvector` PostgreSQL extension with Perl via `DBD::Pg`. It demonstrates how to store and query vector embeddings, perform similarity search, and implement hybrid and sparse retrieval workflows from Perl scripts.

## Features

- **pgvector integration for Perl**  
  - Shows how to use the `vector` column type provided by the `pgvector` extension in PostgreSQL.  
  - Demonstrates creating tables with `vector(dim)` columns.  
  - Example: `CREATE TABLE items (id bigserial PRIMARY KEY, embedding vector(3));`

- **DBD::Pg support**  
  - Designed to work with the `DBD::Pg` Perl database driver.  
  - Uses standard DBI/DBD::Pg patterns for connecting to PostgreSQL, preparing statements, and executing queries.

- **Extension setup**  
  - Example code for enabling the `pgvector` extension in a PostgreSQL database:  
    - `CREATE EXTENSION IF NOT EXISTS vector;`

- **Vector insertion examples**  
  - Demonstrates how to construct vector literals and insert them as parameters via prepared statements.  
  - Example patterns for inserting multiple vector rows into a `vector` column.

- **Similarity search and retrieval use cases**  
  The repository contains end-to-end examples of embedding generation and querying for common retrieval tasks:
  - **Embeddings search with OpenAI**  
    - Example script (`examples/openai/example.pl`) that generates embeddings with OpenAI and stores/queries them in PostgreSQL using pgvector.  
  - **Binary embeddings with Cohere**  
    - Example script (`examples/cohere/example.pl`) for using Cohere’s binary embeddings with pgvector.  
  - **Hybrid search with Ollama**  
    - Example script (`examples/hybrid/example.pl`) illustrating hybrid search using Reciprocal Rank Fusion (RRF) to combine vector and other signals.  
  - **Sparse search with Text Embeddings Inference**  
    - Example script (`examples/sparse/example.pl`) showing sparse retrieval workflows and how to integrate scores into PostgreSQL queries.

- **Standalone example script**  
  - `example.pl` at the repository root demonstrates a minimal setup:  
    - Connecting to PostgreSQL.  
    - Enabling the `vector` extension.  
    - Creating a table with a `vector` column.  
    - Inserting embeddings.  
    - Running basic similarity queries (via SQL using pgvector operators/functions).

- **Automation / CI configuration**  
  - GitHub Actions workflow configuration under `.github/workflows` (e.g., for tests or checks) to ensure examples remain functional.

## Usage

- Install and configure PostgreSQL with the `pgvector` extension.  
- Use `DBD::Pg` from Perl to connect to your PostgreSQL database.  
- Enable the extension in your database (`CREATE EXTENSION IF NOT EXISTS vector;`).  
- Define tables with `vector(dim)` columns and use the provided examples as templates for inserting embeddings and performing similarity, hybrid, or sparse search queries.

## Pricing

- Open-source under the MIT license; no pricing or plans are specified in the repository.