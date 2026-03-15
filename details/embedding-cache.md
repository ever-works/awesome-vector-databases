## Overview

Embedding caches store computed embeddings to avoid redundant API calls. Critical for cost reduction and performance in production systems.

## Why Cache Embeddings?

### Cost Savings
- OpenAI embeddings: $0.13 per 1M tokens
- Repeated content → wasted money
- Cache hit rate of 30-50% typical
- 30-50% cost reduction

### Performance
- API latency: 100-500ms
- Cache lookup: <10ms
- 10-50x faster for cache hits

## Implementation

```python
import hashlib
import redis

class EmbeddingCache:
    def __init__(self, redis_client):
        self.redis = redis_client
        
    def get_embedding(self, text):
        # Create cache key
        key = hashlib.sha256(text.encode()).hexdigest()
        
        # Check cache
        cached = self.redis.get(key)
        if cached:
            return json.loads(cached)
            
        # Compute and cache
        embedding = embedding_model.encode(text)
        self.redis.set(key, json.dumps(embedding), ex=86400)  # 24h TTL
        return embedding
```

## Cache Strategies

### Exact Match
- Hash text content
- 100% accuracy
- Lower hit rate

### Semantic Cache
- Find similar cached texts
- Higher hit rate
- Approximate matches
- Uses vector DB for cache lookup

## GPTCache

Dedicated library for LLM caching:
- Semantic caching
- Multiple backends (Redis, Milvus)
- Similarity thresholds
- TTL management

## Best Practices

1. **Normalize Text**: Lowercase, trim whitespace
2. **Set TTL**: Expire old embeddings
3. **Monitor Hit Rate**: Track cache effectiveness
4. **Size Limits**: Prevent unbounded growth
5. **Invalidation**: Clear when model updates

## Pricing

Cache storage costs (Redis/Memcached) typically < embedding API costs.