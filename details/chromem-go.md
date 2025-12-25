# chromem-go

**Website:** https://github.com/philippgille/chromem-go  
**Category:** Curated Resource Lists  
**Type:** Go library / embeddable vector database

## Description
chromem-go is an embeddable, in-memory vector database for Go that implements Chroma-like functionality. It enables storing embeddings and performing similarity search directly within Go applications, without third-party dependencies, with optional persistence.

## Features
- **Chroma-like interface**
  - API modeled after the Chroma vector database for familiarity and easier porting of existing code.
- **Embeddable in Go applications**
  - Runs as a Go library inside your process; no separate server required.
- **In-memory storage**
  - Keeps vectors and metadata in memory for fast similarity search.
- **Optional persistence**
  - Supports persisting data so collections can be stored and reloaded instead of being purely ephemeral.
- **Embedding storage**
  - Store vector embeddings along with associated documents/metadata.
- **Similarity search**
  - Perform similarity queries over stored embeddings to retrieve the most relevant items.
- **Zero third-party dependencies**
  - Implemented using only the Go standard library, reducing external dependency management.
- **Collections abstraction**
  - Organize embeddings/documents into logical collections for separate indexing and querying.
- **Examples included**
  - `examples/` directory with usage examples.
- **WebAssembly support directory**
  - `wasm/` directory indicating experimental/auxiliary support for WebAssembly-related usage.

## Licensing
- Licensed under the **MPL-2.0** (Mozilla Public License 2.0).

## Pricing
- Open-source library; no pricing information provided (usable under MPL-2.0 license terms).