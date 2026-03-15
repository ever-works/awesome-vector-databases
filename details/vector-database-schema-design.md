## Overview

Vector database schema design determines how vectors and metadata are organized, indexed, and queried. Good design is critical for performance and scalability.

## Schema Components

### Vectors
```json
{
  "embedding": [0.1, 0.2, ...],  // Dense vector
  "sparse_embedding": {1: 0.5, 42: 0.8}  // Sparse vector (optional)
}
```

### Metadata
```json
{
  "id": "doc123",
  "title": "...",
  "category": "technology",
  "timestamp": "2024-01-15",
  "tags": ["AI", "ML"],
  "author": "..."
}
```

## Design Principles

### 1. Index Frequently Filtered Fields
```python
# Index category for fast filtering
collection.create_index(
    field_name="category",
    index_params={"index_type": "HASH"}
)
```

### 2. Denormalize for Performance
- Store author name (not just ID)
- Avoid joins
- Trade storage for speed

### 3. Use Appropriate Data Types
- Integers for IDs
- Timestamps for dates
- Arrays for multi-valued fields
- JSON for nested structures

### 4. Partition Large Collections
```python
# Partition by date
partitions = ["2024-01", "2024-02", "2024-03"]

# Search specific partition
results = collection.search(
    data=query,
    partition_names=["2024-03"]
)
```

## Common Patterns

### Multi-Vector Collections
Separate vectors for different modalities:
```json
{
  "text_embedding": [...],
  "image_embedding": [...],
  "combined_embedding": [...]
}
```

### Hierarchical Organization
- Collections per document type
- Partitions per time range
- Metadata for fine-grained filtering

## Anti-Patterns

- **Over-normalized**: Too many collections
- **Under-indexed**: Missing indexes on filters
- **Large Metadata**: Huge JSON blobs
- **No Partitioning**: Single partition for billions of vectors

## Migration Strategy

1. Design for growth
2. Version your schema
3. Plan for re-indexing
4. Test with production data volume

## Pricing

Not applicable (design practice).