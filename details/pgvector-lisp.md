# pgvector-lisp

**Category:** SDKs & Libraries  
**Brand:** pgvector  
**License:** MIT  
**Source:** https://github.com/pgvector/pgvector-lisp

Lisp bindings and examples for using the pgvector PostgreSQL extension from Common Lisp, supporting multiple database libraries.

---

## Features

### Core Functionality
- Provides Common Lisp examples for integrating with the [pgvector](https://github.com/pgvector/pgvector) PostgreSQL extension.
- Enables using PostgreSQL as a vector store in Common Lisp applications.
- Supports vector operations via existing Common Lisp database libraries.

### Supported Database Libraries
- **Postmodern**
  - Integration examples for using pgvector with the Postmodern PostgreSQL client.
  - Instructions for enabling the `vector` extension in PostgreSQL.
  - Example code for defining tables with vector columns and running queries.
- **CL-DBI**
  - Integration examples for using pgvector with CL-DBI.
  - Example code demonstrating how to work with vector columns via CL-DBI.

### Example Workflows
- **Embeddings with OpenAI**
  - Example showing how to generate embeddings using OpenAI and store/query them in PostgreSQL via pgvector.
- **Binary Embeddings with Cohere**
  - Example demonstrating use of binary embeddings from Cohere with pgvector.
- **Hybrid Search with Ollama**
  - Example of hybrid search combining signals (e.g., using Reciprocal Rank Fusion) with pgvector.
- **Sparse Search with Text Embeddings Inference**
  - Example of sparse vector search using Text Embeddings Inference with pgvector.

### Repository Contents
- `postmodern.lisp` – sample code for Postmodern-based integration.
- `cl-dbi.lisp` – sample code for CL-DBI-based integration.
- `examples/` – multiple end-to-end examples for embeddings, binary embeddings, hybrid search, and sparse search.
- GitHub Actions workflows configuration under `.github/workflows`.

---

## Getting Started
- Choose your database library:
  - Follow the **Postmodern** section for Postmodern-based projects.
  - Follow the **CL-DBI** section for CL-DBI-based projects.
- Use the examples in `examples/` as templates for:
  - Setting up pgvector in PostgreSQL (enabling the `vector` extension).
  - Creating tables with vector (and possibly sparse) columns.
  - Inserting, updating, and querying vector data.

---

## Pricing
- Not applicable. This is an open-source MIT-licensed library with no pricing plans.