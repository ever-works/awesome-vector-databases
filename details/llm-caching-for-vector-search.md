## Why Cache in Vector Search?

- Reduce LLM API costs (major savings)
- Improve latency (10-100x faster)
- Handle rate limits
- Improve reliability
- Better user experience

## Caching Layers

**1. Embedding Cache**:
- Cache computed embeddings
- Key: Source text
- Value: Vector embedding
- TTL: Long (embeddings stable)

**2. Vector Search Cache**:
- Cache search results
- Key: Query embedding
- Value: Retrieved documents
- TTL: Medium (data changes)

**3. LLM Response Cache**:
- Cache complete responses
- Key: Context + query
- Value: Generated answer
- TTL: Short to medium

**4. Semantic Cache**:
- Cache by semantic similarity
- Similar queries → same answer
- Most powerful for RAG

## Semantic Caching

**Concept**:
- Store query embeddings
- Match similar queries (cosine > 0.95)
- Return cached response
- 30-70% cache hit rates possible

**Implementation**:
```python
def semantic_cache_lookup(query):
    query_emb = embed(query)
    similar = cache_index.search(query_emb, threshold=0.95)
    if similar:
        return cached_responses[similar[0]]
    return None
```

**Benefits**:
- Handles query variations
- "What's the weather?" ≈ "Tell me the weather"
- Cost savings 50-80%

## Cache Key Strategies

**Exact Match**:
```python
key = hash(query_text)
```
Simple but misses similar queries

**Semantic Match**:
```python
key = vector_similarity_search(query_embedding)
```
Flexible, higher hit rate

**Hybrid**:
```python
if exact_match: return cached
elif semantic_match > threshold: return cached
else: compute_new
```

## TTL Strategies

**Embedding Cache**: 30+ days
- Embeddings don't change
- Unless model updated

**Search Results**: 1-24 hours
- Depends on data freshness needs
- Balance staleness vs hits

**LLM Responses**: 1-6 hours
- Context may change
- Balance quality vs cost

**Semantic Cache**: 6-24 hours
- Query patterns shift
- Seasonal adjustment

## Cache Technologies

**Redis**:
- Fast in-memory
- TTL support
- Distributed
- Popular choice

**Memcached**:
- Simple, fast
- No persistence
- Good for ephemeral

**DynamoDB**:
- Serverless
- Pay per use
- TTL support

**Vector Databases**:
- Qdrant, Pinecone for semantic cache
- Purpose-built

## Cache Invalidation

**Time-Based**: Simple TTL

**Event-Based**:
- Invalidate when data updates
- Clear affected caches
- More complex but accurate

**Version-Based**:
- Cache key includes version
- Change version to invalidate all

## Cost Impact

**Example Savings**:
- 10K queries/day
- 50% cache hit rate
- $0.001/query (LLM cost)
- Savings: $150/month

At scale:
- 1M queries/day
- 60% cache hit rate
- Savings: $18K/month

## Implementation Best Practices

1. **Start Simple**: Exact match first
2. **Add Semantic**: For common queries
3. **Monitor Hit Rate**: Target 30-50%
4. **Tune Threshold**: Balance quality vs hits
5. **Set Appropriate TTLs**: Test and adjust
6. **Log Cache Events**: Debug and optimize
7. **Handle Cache Failures**: Graceful degradation

## Monitoring Metrics

- Cache hit rate
- Cache miss rate
- Average latency (hit vs miss)
- Cost savings
- Cache size
- Eviction rate

## Common Patterns

**Read-Through**:
```python
result = cache.get(key)
if not result:
    result = compute_expensive()
    cache.set(key, result)
return result
```

**Write-Through**:
```python
result = compute()
cache.set(key, result)
return result
```

**Cache-Aside**:
```python
if key in cache:
    return cache[key]
result = compute()
cache[key] = result
return result
```

## Advanced: GPTCache

Purpose-built semantic caching library:
- Similarity evaluation
- Data management
- Adapter support
- Easy integration

## Pitfalls

1. Over-caching (staleness)
2. Under-caching (poor hit rate)
3. Wrong TTL values
4. Missing cache warming
5. No monitoring
6. Cache stampede
7. Memory exhaustion