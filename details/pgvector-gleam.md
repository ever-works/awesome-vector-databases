# pgvector-gleam

- **Website/Source:** https://github.com/pgvector/pgvector-gleam
- **Category:** SDKs & Libraries
- **Brand:** pgvector
- **Language/Runtime:** Gleam
- **Use case:** Vector similarity search in PostgreSQL from Gleam applications

## Description
pgvector-gleam is a Gleam-language client and example set for using the pgvector PostgreSQL extension. It demonstrates how to store and query vector embeddings in PostgreSQL from Gleam, enabling vector similarity search and related operations. The library provides examples that work with the `pog` Gleam PostgreSQL library.

## Features
- **pgvector integration for Gleam**
  - Example code for interacting with the pgvector PostgreSQL extension from Gleam.
  - Shows how to define and work with vector columns in PostgreSQL tables.

- **Supports `pog` database library**
  - Works with the `pog` Gleam PostgreSQL client.
  - Provides a full example file (`src/pgvector.gleam`) demonstrating usage with `pog`.

- **Database setup guidance**
  - Steps to enable the pgvector extension in PostgreSQL.
  - Example schema definitions to create tables with vector columns.

- **Vector operations workflow**
  - Examples for inserting vectors into PostgreSQL.
  - Queries to retrieve nearest neighbors using pgvector’s similarity search.
  - Instructions for adding an approximate index to accelerate similarity search.

- **Distance and similarity operators**
  - Usage of `vector_ip_ops` for inner product similarity.
  - Usage of `vector_cosine_ops` for cosine distance / similarity.

- **Build & CI ready**
  - GitHub Actions workflow for building and testing the project.
  - Configured with `gleam.toml` and standard project structure under `src/`.

- **Open source project structure**
  - Includes license file (`LICENSE.txt`).
  - Contribution guidelines encouraged via the repository (issues/PRs).

## Pricing
- Not applicable – this is an open-source GitHub repository. No pricing information is provided.
