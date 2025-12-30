# pgvector-rust

**Category:** SDKs & Libraries  
**Tags:** sdk, pgvector, vector-store  
**Source:** https://github.com/pgvector/pgvector-rust

Rust client library for working with the PostgreSQL `pgvector` extension, providing idiomatic Rust APIs for storing embeddings and running similarity queries.

---

## Features

- **Rust bindings for pgvector**  
  - Provides native Rust types and traits to interact with PostgreSQL `pgvector` columns.

- **ORM / client support**  
  - Integrates with popular Rust PostgreSQL clients and ORMs:
    - [Rust-Postgres](https://github.com/sfackler/rust-postgres)
    - [SQLx](https://github.com/launchbadge/sqlx)
    - [Diesel](https://github.com/diesel-rs/diesel)

- **Embedding storage**  
  - Store vector embeddings in PostgreSQL using the `pgvector` extension.

- **Similarity queries**  
  - Run similarity searches (e.g., nearest-neighbor queries) against stored vectors via supported clients/ORMs.

- **Examples included**  
  - Repository contains example projects under the `examples/` directory to demonstrate usage with different Rust database libraries.

- **Versioned and changelogged**  
  - `CHANGELOG.md` maintained for tracking changes across releases.

- **Dual licensing**  
  - Licensed under both **Apache-2.0** and **MIT**, allowing flexible use in open-source or commercial projects.

---

## Licensing

- **Licenses:**
  - Apache-2.0 (`LICENSE-APACHE`)
  - MIT (`LICENSE-MIT`)

---

## Pricing

- Open-source library; no pricing plans are provided in the repository.
