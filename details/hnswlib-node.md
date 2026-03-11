## Overview

hnswlib-node provides Node.js bindings for HNSWlib, enabling approximate nearest-neighbor search based on hierarchical navigable small world graphs in JavaScript and TypeScript applications.

## Key Features

- **HNSW Algorithm**: Fast approximate nearest-neighbor search
- **Multiple Distance Metrics**: L2 (Euclidean), Cosine, Inner Product
- **File Persistence**: Save and load indices to/from disk
- **Filter Functions**: Search with custom filter predicates
- **LangChain Integration**: Compatible with LangChain vector stores
- **Active Development**: Regular updates and maintenance

## Installation

```bash
npm install hnswlib-node
```

Available on npm: https://www.npmjs.com/package/hnswlib-node

## Popularity

- 12,405+ weekly downloads on npm
- Open source under Apache-2.0 License
- Active community and regular updates

## Basic Usage

The library provides a simple API for:
- Creating vector indices with specified dimensions
- Adding vectors to the index
- Searching for nearest neighbors
- Persisting indices to files
- Loading indices from disk

## Use Cases

- **In-Memory Vector Search**: Fast vector similarity search for Node.js applications
- **Machine Learning**: Embedding-based search for ML models
- **Recommendation Systems**: User/item similarity matching
- **Semantic Search**: Text embedding similarity in Node.js backends
- **RAG Applications**: Retrieval component for LangChain-based RAG

## Integration

### LangChain

Integrated as an in-memory vector store in LangChain JavaScript:
- Fast local vector search
- File-based persistence
- No external dependencies required

### Related Projects

- **hnswlib-wasm**: Browser-based HNSW via WebAssembly
- **hnswsqlite**: Persistent vector search combining HNSWlib with SQLite

## Performance

HNSW algorithm provides:
- Logarithmic search complexity
- High recall rates (90%+ typical)
- Fast query times for approximate search
- Efficient memory usage

## API Documentation

Complete API documentation available at:
https://yoshoku.github.io/hnswlib-node/doc/

## Advantages

- **No External Services**: Runs entirely in Node.js process
- **Simple Setup**: Easy npm install, no database server needed
- **File Persistence**: Indices can be saved and loaded
- **Type Safety**: Works well with TypeScript
- **Small Footprint**: Minimal dependencies

## Limitations

- In-memory only (until persisted to disk)
- Not suitable for distributed deployments
- Limited to single-machine scale
- No built-in replication or clustering

## Pricing

Free and open-source under the Apache 2.0 license.