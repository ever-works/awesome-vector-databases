## Overview

Chroma-go is the official Go client library for Chroma vector database, providing a type-safe, idiomatic Go interface for vector storage and retrieval operations.

## Compatibility

- Current release lines (v0.3.x and v0.4.x) are compatible with Chroma v1.x
- Supports both client-server and in-process deployment modes

## Key Features

- **In-Process Storage**: Run Chroma locally using `NewPersistentClient`, with automatic shim library download on first use
- **HNSW Configuration**: Configure HNSW parameters including:
  - `space`: Distance metric (L2, cosine, IP)
  - `ef_construction`: Index construction time quality parameter
  - `ef_search`: Search time accuracy parameter
  - `max_neighbors`: Maximum number of neighbors per node

- **Full API Support**: Complete implementation of Chroma's vector operations
- **Type Safety**: Leverages Go's type system for compile-time safety

## Installation

```bash
go get github.com/amikos-tech/chroma-go
```

## Use Cases

- Building Go-based RAG applications
- Embedding management in Go services
- Vector search for Go microservices
- Integration with Go web frameworks