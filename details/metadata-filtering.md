## Overview

Metadata filtering allows combining vector similarity search with structured attribute filtering. Instead of searching all vectors, you can limit searches to specific subsets matching metadata criteria (e.g., category="tech", date>2024, user_id=123).

## Why Metadata Filtering?

### Common Requirements
- **Access Control**: Filter by user permissions
- **Temporal**: Recent documents only
- **Categorical**: Specific types/tags
- **Multi-Tenancy**: Isolate customer data
- **Status**: Published vs draft
- **Geographic**: Location-based filtering

## Filter Types

### Equality Filters
```
category = "technology"
author_id = 42
status IN ["published", "featured"]
```

### Range Filters
```
date >= "2024-01-01"
price BETWEEN 100 AND 500
rating > 4.0
```

### Composite Filters
```
(category = "tech" AND date > "2024-01-01") 
OR featured = true
```

## Implementation Approaches

### Post-Filtering
1. Retrieve top-k vectors
2. Filter by metadata
3. Return filtered results

**Pros**: Simple
**Cons**: May return too few results, inefficient

### Pre-Filtering
1. Filter by metadata first
2. Search only filtered subset
3. Return top-k from subset

**Pros**: Efficient, guaranteed results
**Cons**: Requires index support

### Hybrid Filtering
1. Combine vector and metadata scores
2. Optimized query planning
3. Used by advanced databases

## Database Support

### Strong Filtering
- **Qdrant**: Excellent filter support
- **Weaviate**: WHERE filters
- **Milvus**: Scalar filtering
- **Elasticsearch**: Bool queries

### Basic Filtering
- **Pinecone**: Metadata filters
- **Chroma**: Where clauses
- **pgvector**: SQL WHERE

## Performance Considerations

### Index Design
- Create indexes on filtered fields
- Compound indexes for multiple filters
- Balance index overhead vs query speed

### Selectivity
- **High Selectivity** (filters to <10%): Very efficient
- **Medium Selectivity** (10-50%): Good performance
- **Low Selectivity** (>50%): Minimal benefit

### Query Optimization
- Filter early when selectivity is high
- Combine filters efficiently
- Use appropriate index types

## Use Cases

### Multi-Tenant SaaS
```python
results = db.search(
    query_vector=embedding,
    filter={"tenant_id": current_user.tenant_id}
)
```

### E-commerce
```python
results = db.search(
    query_vector=embedding,
    filter={
        "category": "electronics",
        "price": {"$lte": 1000},
        "in_stock": True
    }
)
```

### Content Platform
```python
results = db.search(
    query_vector=embedding,
    filter={
        "published_date": {"$gte": "2024-01-01"},
        "status": "published",
        "tags": {"$contains": "python"}
    }
)
```

## Best Practices

1. **Index Frequently Filtered Fields**: Dramatically improves performance
2. **Design for Selectivity**: High-selectivity filters first
3. **Avoid Over-Filtering**: Balance precision vs recall
4. **Test Performance**: Measure impact of filters
5. **Plan for Scale**: Consider filter distribution
6. **Use Appropriate Types**: Numbers for ranges, enums for categories

## Common Pitfalls

### Returning Too Few Results
Problem: Filter is too restrictive
Solution: Retrieve more initially, or relax filters

### Poor Performance
Problem: No indexes on filtered fields
Solution: Create appropriate indexes

### Complex Logic
Problem: Deeply nested boolean expressions
Solution: Simplify or denormalize data

## Advanced Patterns

### Filtered DiskANN
Microsoft's approach:
- Maintains separate indexes per filter value
- Optimized for high-selectivity filters
- Used in Azure Cosmos DB

### Hybrid Queries
Combine multiple search types:
- Vector similarity
- Keyword search (BM25)
- Metadata filters
- Aggregate with RRF

## Integration Examples

### Pinecone
```python
results = index.query(
    vector=query_embedding,
    filter={"genre": {"$eq": "sci-fi"}},
    top_k=10
)
```

### Qdrant
```python
results = client.search(
    collection_name="docs",
    query_vector=query_embedding,
    query_filter=Filter(
        must=[FieldCondition(
            key="category",
            match=MatchValue(value="tech")
        )]
    ),
    limit=10
)
```

## Pricing

Filtering capability included; performance depends on index strategy.