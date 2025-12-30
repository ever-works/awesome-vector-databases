---
title: pgvector-cobol
slug: pgvector-cobol
brand: pgvector
brand_logo: https://avatars.githubusercontent.com/u/101229709
category: sdks-libraries
tags:
  - sdk
  - pgvector
  - vector-store
  - cobol
  - postgresql
  - embeddings
source_url: https://github.com/pgvector/pgvector-cobol
license: MIT
featured: false
images:
  - https://opengraph.githubassets.com/1/pgvector/pgvector-cobol
---

## Overview

pgvector-cobol provides COBOL examples and bindings for the pgvector PostgreSQL extension, enabling legacy COBOL applications (via Open Cobol ESQL) to store and query vector embeddings in PostgreSQL.

## Features

- **COBOL examples for pgvector**
  - Sample COBOL code showing how to work with pgvector from COBOL programs.
  - Includes a complete example program (`example.cbl`).

- **Open Cobol ESQL support**
  - Designed to work with [Open Cobol ESQL](https://github.com/opensourcecobol/Open-COBOL-ESQL).
  - Uses embedded SQL (`EXEC SQL ... END-EXEC`) within COBOL.

- **Extension management**
  - Example for enabling the `vector` extension in PostgreSQL:
    - `EXEC SQL CREATE EXTENSION IF NOT EXISTS vector END-EXEC.`

- **Schema definition for vectors**
  - Example of creating a table with a `vector` column type:
    - `EXEC SQL CREATE TABLE items ( id bigserial PRIMARY KEY, embedding vector(3) ) END-EXEC.`
  - Demonstrates usage of fixed-dimension vectors (e.g., dimension 3).

- **Inserting vector data**
  - Shows how to assign vector values to COBOL variables and insert them into PostgreSQL:
    - Move JSON-like array strings (e.g., `"[1,2,3]"`) into COBOL variables.
    - Insert multiple embeddings into the `vector` column via embedded SQL.

- **Vector similarity search**
  - Example query to retrieve nearest neighbors using pgvector distance operator `<->`:
    - `ORDER BY embedding <-> :EMBEDDING LIMIT 5`
  - Demonstrates selecting the nearest item ID into a COBOL variable.

- **Reference example program**
  - `example.cbl` shows end-to-end flow: enabling extension, creating table, inserting vectors, and querying nearest neighbors.

- **Open-source license**
  - Released under the MIT license.

## Getting Started

- Install and configure Open Cobol ESQL.
- Enable the `vector` extension in your PostgreSQL database from COBOL using:
  - `EXEC SQL CREATE EXTENSION IF NOT EXISTS vector END-EXEC.`
- Follow the `README.md` and `example.cbl` in the repository to:
  - Define tables with `vector` columns.
  - Insert embedding data from COBOL variables.
  - Run nearest neighbor queries with pgvector operators.

## Pricing

- pgvector-cobol is an open-source project released under the MIT license and is free to use.
