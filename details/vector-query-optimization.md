## Overview

Vector query optimization involves tuning search parameters, caching strategies, and query patterns to achieve optimal performance and cost.

## Parameter Tuning

### HNSW Parameters
```python
index_params = {
    "M": 16,  # Connections per layer (higher = better recall, more memory)
    "efConstruction": 200,  # Build quality
}

search_params = {
    "ef": 64  # Search quality (higher = slower, better recall)
}
```

### IVF Parameters
```python
index_params = {
    "nlist": 1024  # Number of clusters
}

search_params = {
    "nprobe": 32  # Clusters to search (higher = slower, better recall)
}
```

## Optimization Techniques

### 1. Batch Queries
```python
# Instead of
for query in queries:
    results = db.search(query)

# Do
results = db.batch_search(queries)  # Much faster
```

### 2. Result Caching
```python
@cache(ttl=3600)
def search(query_text):
    embedding = embed(query_text)
    return db.search(embedding)
```

### 3. Filter Optimization
```python
# Index filtered fields
collection.create_index("category")

# Pre-filter before vector search
results = db.search(
    vector=query,
    filter="category == 'tech'",  # Reduces search space
    limit=10
)
```

### 4. Limit Results
```python
# Don't fetch more than needed
results = db.search(query, limit=10)  # Not 100
```

### 5. Quantization
```python
# Use scalar quantization
index_params = {
    "index_type": "IVF_SQ8",  # 4x memory reduction
}
```

## Cost Optimization

### Reduce Embedding Calls
- Cache embeddings
- Batch embed operations
- Use smaller models where acceptable

### Optimize Storage
- Lower dimensionality (if using MRL)
- Quantization
- Compression

### Right-Size Infrastructure
- Monitor actual usage
- Scale down unused capacity
- Use serverless for variable load

## Monitoring Queries

```python
import time

def search_with_metrics(query):
    start = time.time()
    results = db.search(query)
    latency = time.time() - start
    
    log_metric("search_latency", latency)
    log_metric("result_count", len(results))
    
    return results
```

## Common Bottlenecks

1. **Too many results**: Use smaller limit
2. **Poor filters**: Index filter fields
3. **Large vectors**: Use quantization
4. **High ef/nprobe**: Lower for speed
5. **No caching**: Add result cache

## Best Practices

1. **Profile First**: Measure before optimizing
2. **A/B Test**: Validate optimizations
3. **Monitor Continuously**: Track query performance
4. **Trade-offs**: Balance accuracy vs. speed
5. **Document**: Record parameter choices

## Pricing

Optimizations reduce query costs and infrastructure spend.