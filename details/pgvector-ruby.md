# pgvector-ruby

**Description**

pgvector-ruby is a Ruby library that adds support for the pgvector PostgreSQL extension, enabling vector types and similarity search from Ruby applications. It integrates with the `pg` gem and the Sequel ORM to support AI and embedding-based use cases on PostgreSQL.

**Category:** SDKs & Libraries  
**Tags:** sdk, pgvector, vector-store  
**License:** MIT

---

## Features

- **pgvector integration for Ruby**  
  - Provides Ruby bindings for the pgvector PostgreSQL extension.  
  - Enables storage and querying of vector (embedding) data directly in PostgreSQL.

- **Database driver/ORM support**  
  - Works with the [`pg` gem](https://github.com/ged/ruby-pg).  
  - Supports [Sequel](https://github.com/jeremyevans/sequel) for ORM-style access.

- **Vector operations in PostgreSQL**  
  - Enables use of vector columns in Ruby apps.  
  - Supports similarity search and distance-based queries via PostgreSQL + pgvector (e.g., for AI/ML embeddings, semantic search, recommendation use cases).

- **Examples and reference code**  
  - `examples/` directory demonstrating usage patterns from Ruby with pg and Sequel.  
  - Helps integrate vector operations into existing Ruby/Rails-style stacks.

- **Ruby gem packaging**  
  - Distributed as a standard Ruby gem (`pgvector`).  
  - Includes gemspec, tests, and changelog for version tracking.

---

## Pricing

- Open-source under the MIT License; no commercial pricing tiers are listed.

---

## Source

- GitHub: https://github.com/pgvector/pgvector-ruby
- Main pgvector project: https://github.com/pgvector/pgvector