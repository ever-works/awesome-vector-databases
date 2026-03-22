## Overview

Multi-tenancy enables serving multiple customers (tenants) from shared vector database infrastructure while maintaining data isolation, security, and performance. Critical for SaaS applications using vector search or RAG.

## Isolation Strategies

### 1. Collection/Index Per Tenant
**Approach**: Separate database collection for each tenant

**Advantages:**
- Complete data isolation
- Independent scaling per tenant
- Easy backup/restore
- Simpler security model
- Performance isolation

**Disadvantages:**
- Higher operational overhead
- More expensive (index per tenant)
- Harder to manage at scale (1000s of tenants)
- Resource fragmentation

**Best For**: <100 tenants, high-value customers

### 2. Namespace Isolation
**Approach**: Logical partitions within single collection

**Advantages:**
- Shared index efficiency
- Lower cost
- Easier management
- Good performance

**Disadvantages:**
- No physical isolation
- Shared resources
- Requires namespace support

**Best For**: Medium scale (100-10000 tenants)
**Supported By**: Pinecone, Qdrant

### 3. Metadata Filtering
**Approach**: Single collection with tenant_id filter

**Advantages:**
- Simplest implementation
- Lowest cost
- Easy to scale
- Shared optimization

**Disadvantages:**
- Filter overhead
- No resource isolation
- Security depends on filters
- Potential performance impact

**Best For**: Large scale (1000s-100000s tenants)

## Implementation Examples

### Pinecone Namespaces
```python
# Upsert with namespace
index.upsert(
    vectors=vectors,
    namespace=f"tenant_{tenant_id}"
)

# Query with namespace
results = index.query(
    vector=query_embedding,
    namespace=f"tenant_{tenant_id}",
    top_k=10
)
```

### Metadata Filtering (Qdrant)
```python
client.search(
    collection_name="shared",
    query_vector=embedding,
    query_filter=Filter(
        must=[FieldCondition(
            key="tenant_id",
            match=MatchValue(value=tenant_id)
        )]
    )
)
```

### Collection Per Tenant (Weaviate)
```python
# Create tenant collection
client.schema.create_class({
    "class": f"Documents_Tenant_{tenant_id}",
    "vectorizer": "text2vec-openai"
})

# Query tenant collection
results = client.query.get(
    f"Documents_Tenant_{tenant_id}",
    ["content"]
).with_near_vector({"vector": query_embedding}).do()
```

## Security Considerations

### Data Isolation
- Physical vs logical separation
- Encryption at rest
- Encryption in transit
- Access control lists

### Query Isolation
Prevent cross-tenant queries:
```python
# Always validate tenant_id
def search(user, query):
    tenant_id = get_tenant_id(user)
    if not is_authorized(user, tenant_id):
        raise UnauthorizedError()
    
    return vector_db.search(
        query,
        filter={"tenant_id": tenant_id}
    )
```

### Rate Limiting
- Per-tenant quotas
- Prevent noisy neighbors
- Fair resource allocation

## Performance Considerations

### Filter Selectivity
Metadata filtering efficiency:
- High selectivity (<10%): Good
- Medium selectivity (10-50%): Okay
- Low selectivity (>50%): Poor

### Index Strategy
For metadata filtering:
- Index tenant_id field
- Composite indexes if needed
- Monitor query performance

### Resource Allocation
Prevent tenant monopolization:
- Query timeouts
- Concurrency limits
- Memory caps
- CPU throttling

## Cost Optimization

### Shared Infrastructure
```
Collection per tenant:
  100 tenants × $70/month = $7,000/month

Shared with filtering:
  1 large collection = $200/month
  95% cost savings!
```

### Hybrid Approach
- Large tenants: Dedicated collections
- Small tenants: Shared collection
- Optimize cost vs performance

## Scaling Patterns

### Vertical
- Bigger instances
- More RAM/CPU
- Limited scalability

### Horizontal
- Shard by tenant_id
- Distribute across instances
- Better for massive scale

### Tiered
- Hot tenants: Dedicated
- Warm tenants: Namespaces
- Cold tenants: Shared filtered

## Migration Strategies

### Starting Point
Small scale (filtering):
- Simple, low cost
- Easy to implement

### Growth Path
1. Filtering (0-1000 tenants)
2. Namespaces (1000-10000 tenants)
3. Hybrid (10000+ tenants)
4. Dedicated for enterprise

## Monitoring

Per-tenant metrics:
- Query volume
- Latency (P50, P95, P99)
- Error rates
- Storage usage
- Costs

## Best Practices

1. **Start Simple**: Filtering sufficient initially
2. **Plan for Growth**: Design for scale
3. **Monitor Per-Tenant**: Track resource usage
4. **Enforce Isolation**: Never mix tenant data
5. **Test Security**: Verify data separation
6. **Document Strategy**: Clear tenant model
7. **Cost Management**: Track and optimize

## Common Pitfalls

### Missing Filters
```python
# BAD: No tenant filter
results = db.search(query)

# GOOD: Always filter
results = db.search(
    query,
    filter={"tenant_id": validated_tenant_id}
)
```

### Performance Degradation
- Monitor as tenant count grows
- Benchmark at scale
- Plan migration early

### Security Gaps
- Test cross-tenant isolation
- Audit access controls
- Penetration testing

## Pricing

Costs vary dramatically by strategy; filtering cheapest, dedicated most expensive.