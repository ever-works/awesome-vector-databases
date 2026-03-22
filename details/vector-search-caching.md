## Overview

Vector search caching stores frequently accessed embeddings and search results to avoid redundant computations. Critical for improving latency and reducing costs in production RAG systems.

## What to Cache

### Query Embeddings
**Cache**: Text → Vector mappings
**Hit Rate**: 20-40% for common queries
**Storage**: Small (KB per entry)
**Benefit**: Skip embedding API call (50-200ms)

### Search Results
**Cache**: (Query embedding, k) → Results
**Hit Rate**: 10-30%
**Storage**: Medium (depends on k)
**Benefit**: Skip vector search (10-100ms)

### Document Embeddings
**Cache**: Document ID → Vector
**Hit Rate**: Near 100% (static docs)
**Storage**: Large (vectors * dimensionality)
**Benefit**: Skip re-embedding documents

## Caching Strategies

### Exact Match Caching
Cache identical queries:
```python
import hashlib

def get_cached_embedding(text, cache):
    key = hashlib.md5(text.encode()).hexdigest()
    if key in cache:
        return cache[key]
    embedding = api.embed(text)
    cache[key] = embedding
    return embedding
```

**Advantages**: Simple, fast
**Disadvantages**: Low hit rate (queries vary)

### Semantic Caching
Cache similar queries:
```python
def semantic_cache_lookup(query_embedding, cache, threshold=0.95):
    for cached_query, results in cache.items():
        similarity = cosine_similarity(
            query_embedding,
            cached_query["embedding"]
        )
        if similarity > threshold:
            return results
    return None
```

**Advantages**: Higher hit rate
**Disadvantages**: Requires similarity search on cache

### Two-Tier Caching
Combine both approaches:
1. Check exact match cache (fast)
2. Check semantic cache (slower but more hits)
3. Compute if both miss

## Cache Invalidation

### Time-Based (TTL)
```python
from datetime import datetime, timedelta

class CacheEntry:
    def __init__(self, value, ttl_seconds=3600):
        self.value = value
        self.expires_at = datetime.now() + timedelta(seconds=ttl_seconds)
    
    def is_valid(self):
        return datetime.now() < self.expires_at
```

**Typical TTLs:**
- Query embeddings: 1-24 hours
- Search results: 5-60 minutes
- Document embeddings: Infinite (until doc changes)

### Event-Based
Invalidate on changes:
- Document update → clear related caches
- Index rebuild → clear search caches
- Model change → clear all embeddings

### LRU (Least Recently Used)
Evict oldest entries:
```python
from functools import lru_cache

@lru_cache(maxsize=10000)
def get_embedding(text):
    return api.embed(text)
```

## Implementation Examples

### Redis Cache
```python
import redis
import pickle

r = redis.Redis()

def cached_search(query_embedding, k=10, ttl=300):
    # Create cache key
    key = f"search:{hash(query_embedding.tobytes())}:{k}"
    
    # Check cache
    cached = r.get(key)
    if cached:
        return pickle.loads(cached)
    
    # Perform search
    results = vector_db.search(query_embedding, k=k)
    
    # Cache results
    r.setex(key, ttl, pickle.dumps(results))
    return results
```

### GPTCache
Specialized library:
```python
from gptcache import Cache
from gptcache.manager import get_data_manager
from gptcache.similarity_evaluation import SearchDistanceEvaluation

cache = Cache()
cache.init(
    embedding_func=embed_func,
    data_manager=get_data_manager(),
    similarity_evaluation=SearchDistanceEvaluation(),
)

# Automatic caching
response = cache.get(query)
if response is None:
    response = llm.generate(query)
    cache.set(query, response)
```

### In-Memory Cache
```python
from collections import OrderedDict

class LRUCache:
    def __init__(self, capacity):
        self.cache = OrderedDict()
        self.capacity = capacity
    
    def get(self, key):
        if key not in self.cache:
            return None
        self.cache.move_to_end(key)
        return self.cache[key]
    
    def put(self, key, value):
        if key in self.cache:
            self.cache.move_to_end(key)
        self.cache[key] = value
        if len(self.cache) > self.capacity:
            self.cache.popitem(last=False)
```

## Performance Impact

### Latency Reduction
```
No Cache:
  Embedding: 100ms
  Search: 50ms
  Total: 150ms

With Cache (80% hit rate):
  Cache hit: 1ms (80% of time)
  Cache miss: 150ms (20% of time)
  Average: 31ms (5x faster!)
```

### Cost Savings
```
1M queries/month:
  No cache: 1M × $0.0001 = $100
  With 50% hit rate: 500K × $0.0001 = $50
  Savings: $50/month
```

## Cache Sizing

### Memory Requirements
```
Query embeddings (1536-dim, float32):
  1 embedding = 1536 × 4 bytes = 6KB
  10,000 queries = 60MB
  100,000 queries = 600MB

Search results (10 docs, 1KB metadata each):
  1 result set = 10KB
  10,000 results = 100MB
```

### Capacity Planning
- Monitor hit rates
- Adjust cache size based on memory
- Balance cost vs performance

## Monitoring

### Key Metrics
- **Hit Rate**: Cached / Total requests
- **Miss Rate**: 1 - Hit Rate
- **Latency**: Cache vs no-cache
- **Memory Usage**: Current vs capacity
- **Eviction Rate**: Entries removed

### Targets
- Hit rate: >30% (good), >50% (excellent)
- P95 latency: <50ms
- Memory usage: <80% capacity

## Best Practices

1. **Cache Embeddings First**: Biggest latency win
2. **Semantic Caching**: For higher hit rates
3. **Appropriate TTLs**: Balance freshness vs hits
4. **Monitor Hit Rates**: Optimize cache size
5. **Warm Cache**: Pre-populate common queries
6. **Distributed Cache**: Redis for multi-instance
7. **Graceful Degradation**: Handle cache failures

## Trade-offs

**Advantages:**
- Lower latency
- Reduced API costs
- Better user experience
- Lower load on vector DB

**Disadvantages:**
- Stale results possible
- Memory overhead
- Complexity
- Cache management

## Pricing

In-memory caching included; Redis costs $20-200+/month depending on size.