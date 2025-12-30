# pgvector-elixir

Elixir wrapper for the pgvector PostgreSQL extension, providing vector types and similarity search support for Elixir applications using Ecto and Postgrex.

---

## Overview
- **Type**: SDK / Library
- **Ecosystem**: Elixir, PostgreSQL (pgvector)
- **Category**: sdks-libraries
- **License**: MIT
- **Source**: https://github.com/pgvector/pgvector-elixir

---

## Features

### Core Functionality
- Elixir support for the [pgvector](https://github.com/pgvector/pgvector) PostgreSQL extension
- Integration with:
  - [Ecto](https://github.com/elixir-ecto/ecto)
  - [Postgrex](https://github.com/elixir-ecto/postgrex)
- Provides vector column support for PostgreSQL-backed Elixir applications
- Enables similarity / vector search workflows via pgvector from Elixir code

### Usage & Integration
- Distributed as a Hex dependency for Elixir projects
- Simple dependency declaration in `mix.exs`:
  ```elixir
  {:pgvector, "~> 0.3.0"}
  ```
- Separate setup instructions for:
  - Ecto-based applications
  - Postgrex-based usage without Ecto
- Includes an `examples` directory demonstrating practical usage patterns

### Development & Maintenance
- Changelog (`CHANGELOG.md`) documenting releases and changes
- Automated workflows under `.github/workflows` (e.g., CI) for testing/quality
- Test suite under `test/` for reliability

---

## Pricing
- Open-source library available under the **MIT License**
- No paid plans mentioned; free to use under the terms of the MIT license.