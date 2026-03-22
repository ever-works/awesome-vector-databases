## Overview

sqlite-vss (SQLite Vector Similarity Search) is a SQLite extension that brings vector search capabilities to SQLite databases using the FAISS library. It enables building semantic search engines, recommendation systems, and question-answering tools directly within SQLite.

## Important Note

The development effort has shifted to sqlite-vec, which is easier to install and use. sqlite-vec is written in pure C with no dependencies and runs anywhere SQLite runs (Linux, macOS, Windows, browsers with WASM, Raspberry Pi).

## Key Features

- **FAISS Integration**: Leverages the powerful FAISS library for approximate nearest neighbor search
- **FTS5-like API**: Similar API to SQLite's fts5 Full-Text Search Extension for familiarity
- **Bring-Your-Own-Vectors**: Compatible with any embedding or vector data
- **K-Nearest Neighbors**: Supports similarity search using the `vss_search` function

## Dependencies

Requires the vector0 extension to be loaded before vss0.

## Platform Support

- Python bindings
- Node.js bindings
- Integration with frameworks like LangChain for AI applications

## Use Cases

- Semantic search within SQLite databases
- Building recommendation engines
- Question-answering systems
- Lightweight vector search for embedded applications