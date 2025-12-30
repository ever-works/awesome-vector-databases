# pgvector-haskell

**Category:** SDKs & Libraries  
**Brand:** pgvector  
**License:** MIT  
**Language:** Haskell

Haskell bindings for the pgvector PostgreSQL extension, allowing Haskell applications to use PostgreSQL as a vector database. Designed to work with the `postgresql-simple` library.

---

## Features

- **Haskell bindings for pgvector**  
  - Provides types and functions to work with pgvector columns from Haskell code.
  - Enables storage and retrieval of vector data in PostgreSQL using the pgvector extension.

- **Integration with `postgresql-simple`**  
  - Explicit support for the `postgresql-simple` Haskell database library.  
  - Library can be imported via:
    ```haskell
    import Pgvector
    ```

- **Database extension support**  
  - Intended to be used with the PostgreSQL `pgvector` extension (e.g., enabling via `CREATE EXTENSION` in SQL).  
  - Bridges Haskell types to the underlying `vector` column type provided by pgvector.

- **Hackage-style dependency management**  
  - Distributed as a Haskell package named `pgvector`.  
  - Can be added to a `.cabal` file with version bounds, e.g.:
    ```cabal
    build-depends: pgvector >= 0.1 && < 0.2
    ```

- **Versioned and changelogged**  
  - Includes a `CHANGELOG.md` for tracking changes across releases.

---

## Installation & Setup

- Add to your `.cabal` file under `build-depends`:
  ```cabal
  pgvector >= 0.1 && < 0.2
  ```
- Ensure the PostgreSQL `pgvector` extension is installed and enabled in your database (e.g., via `CREATE EXTENSION pgvector;`).
- Use with the `postgresql-simple` library in your Haskell application.

---

## Pricing

- Open source, available under the MIT license (no usage fee).