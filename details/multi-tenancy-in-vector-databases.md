## What is Multi-Tenancy?

Multi-tenancy allows multiple customers (tenants) to share the same database infrastructure while maintaining data isolation, security, and performance.

## Why Multi-Tenancy for Vector DBs?

**Benefits**:
- Cost efficiency (shared infrastructure)
- Easier management (single deployment)
- Resource pooling
- Faster provisioning

**Challenges**:
- Data isolation
- Performance isolation (noisy neighbors)
- Security boundaries
- Scaling complexity

## Isolation Strategies

### 1. Separate Databases

**Approach**: One database per tenant

**Pros**:
- Strong isolation
- Easy backup/restore per tenant
- Simple security model
- Independent scaling

**Cons**:
- High operational overhead
- Expensive at scale
- Complex management
- Resource waste (over-provisioning)

**Best For**: Enterprise customers, strict compliance

### 2. Separate Collections/Indexes

**Approach**: Shared database, separate collections per tenant

**Pros**:
- Good isolation
- Easier than separate DBs
- Per-tenant configuration
- Simpler management

**Cons**:
- Collection limit constraints
- Still some operational overhead
- Shared resource contention

**Best For**: Mid-market, 100s-1000s of tenants

### 3. Partition Keys

**Approach**: Single collection with tenant_id as partition key

**Pros**:
- Most efficient
- Minimal overhead
- Scales to millions of tenants
- Simple operations

**Cons**:
- Relies on correct filtering
- Risk of data leakage
- Limited per-tenant config
- Shared performance

**Best For**: SMB, high tenant count

### 4. Hybrid Approach

**Approach**: Tier-based isolation
- Enterprise: Separate databases
- Business: Separate collections
- Free/Starter: Partition keys

**Best For**: SaaS with multiple tiers

## Implementation Patterns

### Partition Key Pattern

```python
# Insert with tenant_id
db.insert(
    id="doc1",
    vector=embedding,
    metadata={"tenant_id": "acme-corp", ...}
)

# Query with tenant filter
results = db.search(
    query_vector=embedding,
    filter={"tenant_id": "acme-corp"},
    k=10
)
```

**Critical**: ALWAYS include tenant_id in queries!

### Namespace Pattern

```python
# Weaviate-style
collection = client.collection(
    name="documents",
    tenant="acme-corp"
)

results = collection.query.near_vector(
    near_vector=embedding,
    limit=10
)
```

## Security Considerations

**1. Query-Time Filtering**:
```python
# Bad: Trusting client
filter = request.filter  # Dangerous!

# Good: Enforce tenant_id
filter = {**request.filter, "tenant_id": current_user.tenant_id}
```

**2. API Key Scoping**:
- Associate keys with tenants
- Validate on every request
- Audit key usage

**3. Row-Level Security**:
- Database-enforced policies
- Can't be bypassed
- PostgreSQL RLS example

**4. Tenant Verification**:
```python
def verify_tenant_access(user, resource):
    if user.tenant_id != resource.tenant_id:
        raise UnauthorizedError()
```

## Performance Isolation

**Resource Quotas**:
- QPS limits per tenant
- Storage limits
- Compute limits

**Rate Limiting**:
```python
@rate_limit("100/minute", key="tenant_id")
def search(request):
    ...
```

**Priority Queuing**:
- Enterprise gets priority
- Free tier deprioritized
- Fair queuing within tier

## Monitoring Per-Tenant

**Metrics to Track**:
- Query count per tenant
- Latency by tenant
- Storage usage
- Error rates
- Cost attribution

**Alerting**:
- Quota exceeded
- Anomalous usage
- Performance degradation
- Security events

## Scaling Strategies

**Horizontal Sharding**:
- Shard by tenant_id
- Route based on tenant
- Balance load

**Tenant Migration**:
- Move large tenants to dedicated
- Rebalance shards
- Zero-downtime migration

**Tiering**:
- Hot tenants: SSD, more resources
- Cold tenants: HDD, shared resources

## Cost Attribution

**Track Per-Tenant**:
```python
# Log with tenant_id
log_cost(
    tenant_id=tenant_id,
    operation="search",
    cost=calculate_cost(query)
)
```

**Billing**:
- Usage-based pricing
- Per-tenant reports
- Quota management

## Data Isolation Testing

**Critical Tests**:
```python
def test_tenant_isolation():
    # Tenant A data
    db.insert("a1", vector_a, {"tenant_id": "A"})
    
    # Tenant B data
    db.insert("b1", vector_b, {"tenant_id": "B"})
    
    # Query as Tenant A
    results = db.search(
        vector_a,
        filter={"tenant_id": "A"}
    )
    
    # Should NEVER see Tenant B data
    assert all(r.metadata["tenant_id"] == "A" for r in results)
```

## Database Support

**Native Multi-Tenancy**:
- Weaviate (namespace-based)
- Qdrant (payload filtering)
- Pinecone (namespaces)

**Manual Implementation**:
- PostgreSQL + pgvector (RLS)
- Milvus (partition keys)
- Chroma (metadata filtering)

## Best Practices

1. **Enforce at API Layer**: Don't trust clients
2. **Test Isolation Rigorously**: Critical for security
3. **Monitor Per-Tenant**: Detect issues early
4. **Implement Quotas**: Prevent abuse
5. **Plan for Growth**: Shard strategy from day one
6. **Document Boundaries**: Clear isolation model
7. **Audit Access**: Who accessed what
8. **Test Migration**: Be able to move tenants
9. **Cost Attribution**: Track spending
10. **Security Reviews**: Regular audits

## Common Pitfalls

1. **Forgetting tenant_id in queries**: Data leak!
2. **No resource limits**: One tenant kills all
3. **Inadequate testing**: Isolation bugs
4. **No monitoring**: Can't detect issues
5. **Hard-coded configs**: Not per-tenant
6. **No migration plan**: Stuck with initial choice
7. **Trusting client filters**: Security hole

## Migration Between Models

**Partition → Collection**:
1. Create new collection for tenant
2. Copy data with background job
3. Dual-write during transition
4. Switch read traffic
5. Verify and cleanup

**Collection → Database**:
1. Provision new database
2. Snapshot and restore
3. Update routing
4. Verify and cleanup

## When to Choose Each

**Partition Keys**: Default for SaaS
**Collections**: 100s of tenants, need isolation
**Databases**: Enterprise, strict compliance
**Hybrid**: Multiple customer tiers