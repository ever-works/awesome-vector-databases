# pgvector-swift

**Category:** SDKs & Libraries  
**Brand:** pgvector  
**Source:** https://github.com/pgvector/pgvector-swift

Swift bindings and examples for using the [pgvector](https://github.com/pgvector/pgvector) PostgreSQL extension from Swift and server-side Swift applications.

---

## Features

- **pgvector integration for Swift**  
  - Provides Swift support for the pgvector extension in PostgreSQL.  
  - Enables use of PostgreSQL as a vector database from Swift and server-side Swift apps.

- **Database driver support**  
  - Works with **PostgresNIO** (Vapor ecosystem).  
  - Works with **PostgresClientKit**.

- **Swift Package Manager compatible**  
  - Distributed as a Swift Package.  
  - Can be added to `Package.swift` for both PostgresNIO and PostgresClientKit projects.

- **Type registration and extensions**  
  - Provides extensions for the supported database clients so they can handle pgvector types.  
  - Includes steps to **enable the extension** and **register vector types** when configuring the database.

- **Schema and operations support**  
  - Examples for creating tables that store vector columns.  
  - Sample code to **insert vectors** into PostgreSQL.  
  - Sample queries to **retrieve nearest neighbors** using pgvector.

- **Indexing and search configuration**  
  - Demonstrates how to add an **approximate index** for vector similarity search.  
  - Shows how to use pgvector operator classes:
    - `vector_ip_ops` for **inner product** similarity.  
    - `vector_cosine_ops` for **cosine distance** similarity.

- **Reference examples and tests**  
  - Example code provided under `Examples/`.  
  - Full usage examples for:
    - PostgresNIO: `Tests/PgvectorTests/PostgresNIOTests.swift`  
    - PostgresClientKit: tests/examples under `Tests/PgvectorTests`.

- **Open source**  
  - Source code and changelog available in the repository.  
  - Licensed under the terms in `LICENSE.txt` (see repo for exact license).

---

## Pricing

- **Free and open source**  
  - No pricing tiers are listed; usage is governed by the open-source license in `LICENSE.txt`.

---

## Links

- Repository: https://github.com/pgvector/pgvector-swift  
- pgvector project: https://github.com/pgvector/pgvector  
- Supported clients:
  - PostgresNIO: https://github.com/vapor/postgres-nio  
  - PostgresClientKit: https://github.com/codewinsdotcom/PostgresClientKit