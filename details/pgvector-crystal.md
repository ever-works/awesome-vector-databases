# pgvector-crystal

Crystal language examples and client usage for pgvector, showing how to work with vector operations in PostgreSQL from Crystal.

- **Category:** SDKs & Libraries  
- **Tags:** sdk, pgvector, vector-store  
- **Language / Stack:** Crystal, PostgreSQL, pgvector  
- **License:** MIT  
- **Source:** https://github.com/pgvector/pgvector-crystal

---

## Overview

`pgvector-crystal` provides example code and patterns for using the pgvector extension from Crystal, with support for the `crystal-pg` PostgreSQL driver. It demonstrates how to perform vector similarity and related operations in PostgreSQL from Crystal-based applications.

---

## Features

- **pgvector integration examples for Crystal**  
  - Demonstrates how to use the pgvector PostgreSQL extension from Crystal code.

- **Support for `crystal-pg`**  
  - Examples are built around the `crystal-pg` database library.

- **Embeddings workflows**  
  - Example for using embeddings with OpenAI:  
    - How to generate embeddings via OpenAI.  
    - How to store and query them with pgvector.

- **Binary embeddings**  
  - Example for using binary embeddings with Cohere:  
    - Handling binary embedding representations.  
    - Integration with pgvector for storage and search.

- **Hybrid search**  
  - Example with Ollama using Reciprocal Rank Fusion (RRF):  
    - Combining multiple ranking signals (e.g., vector and keyword scores).  
    - Demonstrates hybrid search patterns with pgvector.

- **Sparse search**  
  - Example of sparse search using text embeddings:  
    - Handling sparse vector representations.  
    - Querying sparse vectors stored in PostgreSQL.

- **Example directory structure**  
  - `examples/openai/example.cr` – embeddings with OpenAI.  
  - `examples/cohere/example.cr` – binary embeddings with Cohere.  
  - `examples/hybrid/example.cr` – hybrid search with Ollama (RRF).  
  - `examples/sparse/example.cr` – sparse search with text embeddings.

---

## Getting Started

- Follow the setup instructions for your database library:  
  - **crystal-pg**: primary supported driver (see README in the repository for exact steps).
- Explore the provided Crystal example files in the `examples/` directory to learn specific integration patterns.

---

## Pricing

- Not applicable. This is an open-source project released under the MIT license.
