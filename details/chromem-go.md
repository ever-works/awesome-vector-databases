## Overview

chromem-go is an embeddable vector database for Go applications with a Chroma-like interface. It's a standalone database (not a Chroma client) with zero third-party dependencies, operating in-memory with optional persistence.

## Key Features

### Embeddability

- **No Separate Database**: Runs inside your Go application
- **Zero Dependencies**: No external libraries required
- **RAG Enablement**: Add retrieval-augmented generation to Go apps
- **Simple Integration**: Import and use as a Go package

### Performance

Optimized for common use cases:
- **1,000 documents**: 0.3 ms query time
- **100,000 documents**: 40 ms query time
- Tested on mid-range 2020 Intel laptop CPU
- Focus on simplicity over massive scale

## Pricing

Free and open-source.