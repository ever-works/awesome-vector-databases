# pgvector-prolog

**Category:** SDKs & Libraries  
**Brand:** pgvector  
**License:** MIT  
**Source:** https://github.com/pgvector/pgvector-prolog

Prolog examples for using the [pgvector](https://github.com/pgvector/pgvector) PostgreSQL extension via the `postgresql-prolog` client, enabling Prolog programs to work with vector data and perform vector similarity search in PostgreSQL.

---

## Features

- **Prolog integration with pgvector**
  - Example code showing how to use the pgvector extension from Prolog.
  - Built around the [`postgresql-prolog`](https://github.com/aarroyoc/postgresql-prolog) database library.

- **Database setup examples**
  - Enabling the `vector` extension in PostgreSQL:
    - `CREATE EXTENSION IF NOT EXISTS vector`.
  - Creating a table with a vector column:
    - Example: `CREATE TABLE items (id bigserial PRIMARY KEY, embedding vector(3))`.

- **Vector data operations**
  - Inserting vector embeddings from Prolog into a `vector` column.
    - Example pattern: inserting `[1,2,3]` into `embedding`.
  - Querying nearest neighbors using pgvector distance operators:
    - Example: `SELECT * FROM items ORDER BY embedding <-> '[3,1,2]' LIMIT 5`.

- **Example Prolog script**
  - `example.pl` demonstrates:
    - Connecting to PostgreSQL via `postgresql-prolog`.
    - Executing SQL statements to enable the extension and create tables.
    - Inserting and querying vector data.

- **CI / workflow configuration**
  - GitHub Actions workflows included under `.github/workflows` (e.g., for basic automation / checks on the repo).

---

## Getting Started

1. Install and configure `postgresql-prolog`.
2. Enable the `vector` extension in your PostgreSQL database:
   - `CREATE EXTENSION IF NOT EXISTS vector`.
3. Create a table with a `vector` column (e.g., `embedding vector(3)`).
4. Use the examples in `example.pl` to:
   - Insert vector embeddings.
   - Run similarity search queries (nearest neighbors) from Prolog.

---

## Pricing

- Not applicable. This is an open-source library released under the MIT license and is free to use.
