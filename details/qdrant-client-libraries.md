## Overview

Qdrant provides official client libraries and SDKs across multiple programming languages, all built from OpenAPI v3 specifications. This ensures consistent APIs and makes it easy to generate clients for additional languages.

## Official SDKs

### Python
```bash
pip install qdrant-client
```
- Async/sync support
- Type hints
- Comprehensive documentation
- Integration with popular ML frameworks

### Rust
```toml
qdrant-client = "1.x"
```
- Native Rust implementation
- High performance
- Type safety
- Zero-cost abstractions

### Go
```bash
go get github.com/qdrant/go-client
```
- Idiomatic Go code
- Context support
- gRPC and REST support

### TypeScript/JavaScript
```bash
npm install @qdrant/js-client-rest
```
- TypeScript definitions
- Browser and Node.js compatible
- Promise-based API

## Additional Languages

- **Java/Kotlin**: Community-maintained
- **.NET/C#**: Official client available
- **PHP**: Community SDK
- **Ruby**: Via REST API

## OpenAPI Advantage

Qdrant uses OpenAPI v3 specifications, enabling:
- Automatic client generation for any language
- Consistent API across all clients
- Up-to-date documentation
- Swagger UI for testing

## Key Features

### Connection Management
- HTTP and gRPC support
- TLS/SSL encryption
- API key authentication
- Connection pooling

### Collection Operations
- Create collections with custom schemas
- Vector configuration (size, distance metric)
- Payload indexing
- Snapshots and backups

### Data Operations
- Upsert points (vectors + payload)
- Batch operations
- Update payloads
- Delete by ID or filter
- Scroll through all points

### Search Capabilities
- Vector similarity search
- Filtered search with complex conditions
- Recommendation API
- Hybrid search (dense + sparse)
- Multi-vector search
- Discovery/context search

### Advanced Features
- **Quantization**: Scalar and binary quantization support
- **Sharding**: Distributed collections
- **Replication**: High availability
- **Snapshots**: Backup and restore
- **Payload Indexing**: Fast metadata filtering

## Python Example

```python
from qdrant_client import QdrantClient
from qdrant_client.models import Distance, VectorParams

client = QdrantClient(url="http://localhost:6333")

# Create collection
client.create_collection(
    collection_name="my_collection",
    vectors_config=VectorParams(size=384, distance=Distance.COSINE),
)

# Upsert vectors
client.upsert(
    collection_name="my_collection",
    points=[
        {"id": 1, "vector": [...], "payload": {"city": "Berlin"}},
        {"id": 2, "vector": [...], "payload": {"city": "London"}},
    ]
)

# Search
results = client.search(
    collection_name="my_collection",
    query_vector=[...],
    limit=10,
    query_filter={"must": [{"key": "city", "match": {"value": "Berlin"}}]}
)
```

## Deployment Options

All SDKs support:
- Qdrant Open Source (self-hosted)
- Qdrant Cloud (managed service)
- Qdrant Hybrid Cloud
- Local in-memory mode (for testing)

## Performance Features

- Batch operations for high throughput
- gRPC for lower latency
- Async operations in Python
- Connection pooling
- Parallel search requests

## Documentation

- API Reference: qdrant.tech/documentation
- Code examples in multiple languages
- Interactive Swagger UI
- Tutorials and guides

## Migration Tools

Qdrant provides migration utilities from:
- Pinecone
- Weaviate
- Milvus
- Elasticsearch

## Pricing

Free and open-source for self-hosted Qdrant. Qdrant Cloud pricing is usage-based.