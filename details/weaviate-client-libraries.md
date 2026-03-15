## Overview

Weaviate provides official client libraries in multiple languages, offering both REST and GraphQL APIs for vector search, hybrid queries, and AI-powered generative search.

## Supported Languages

### Python
```bash
pip install weaviate-client
```
- Full feature support
- Type hints
- Async operations
- Batch imports

### TypeScript/JavaScript  
```bash
npm install weaviate-ts-client
```
- Browser and Node.js
- Promise-based
- TypeScript definitions

### Go
```bash
go get github.com/weaviate/weaviate-go-client/v4
```
- Native Go implementation
- Idiomatic API

### Java
```xml
<dependency>
    <groupId>io.weaviate</groupId>
    <artifactId>client</artifactId>
</dependency>
```

## Key Features

- Vector search
- Hybrid search (vector + keyword)
- Generative search (RAG)
- GraphQL queries
- Batch operations
- Multi-tenancy support
- Named vectors

## Example Usage

```python
import weaviate

client = weaviate.Client("http://localhost:8080")

# Vector search
results = (
    client.query
    .get("Article", ["title", "content"])
    .with_near_text({"concepts": ["AI"]})
    .with_limit(10)
    .do()
)

# Hybrid search
results = (
    client.query
    .get("Article", ["title"])
    .with_hybrid(query="AI", alpha=0.5)
    .do()
)
```

## Pricing

Free and open-source. Weaviate Cloud pricing separate.