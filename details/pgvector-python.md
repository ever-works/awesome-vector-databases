---
name: pgvector-python
slug: pgvector-python
url: https://github.com/pgvector/pgvector-python
category: sdks-libraries
brand: pgvector
brand_logo: https://avatars.githubusercontent.com/u/101229709
images:
  - https://opengraph.githubassets.com/1/pgvector/pgvector-python
tags:
  - sdk
  - pgvector
  - vector-store
license: MIT
featured: false

summary: |
  Python library for working with the pgvector PostgreSQL extension, enabling storage and similarity search of vector embeddings from Python-based AI/ML workflows and popular Python ORMs.

features: |
  - Native Python client for pgvector, the PostgreSQL extension for vector similarity search
  - Integrates PostgreSQL vector storage with Python AI/ML pipelines
  - Support for popular Python frameworks and ORMs, including Django and SQLAlchemy (and likely other DB abstraction layers such as SQLModel)
  - Provides tools to store, query, and compare vector embeddings directly in PostgreSQL
  - Enables similarity search and nearest-neighbor queries on vector data
  - Example code included (in `examples/`) to demonstrate usage patterns and integrations
  - Test suite (in `tests/`) for validating behavior and integrations
  - Distributed as a standard Python package (configured via `pyproject.toml`)
  - Open-source under the MIT license

use_cases: |
  - Persisting embedding vectors (from models such as sentence transformers or other embedding models) in PostgreSQL via pgvector from Python code
  - Implementing semantic search or recommendation systems using vector similarity queries in Python applications
  - Integrating vector search into Django- or SQLAlchemy-based web applications
  - Prototyping and experimenting with pgvector functionality using the included Python examples

pricing: |
  - Open source, MIT-licensed (no paid plans listed)

notes: |
  - Full feature set and detailed integration examples are available in the repository’s README and examples directory.
