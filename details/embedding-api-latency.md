## Overview

Embedding API latency is the time to convert text/data into vector embeddings. This is often the bottleneck in RAG pipelines, especially for user-facing applications requiring sub-second response times.

## Typical Latency Ranges

### Commercial APIs
- **OpenAI**: 50-200ms (single), 100-500ms (batch)
- **Cohere**: 30-150ms (single), 50-300ms (batch)
- **Voyage AI**: 40-180ms
- **Google Vertex AI**: 50-250ms

### Self-Hosted
- **CPU (small model)**: 20-100ms
- **CPU (large model)**: 100-500ms
- **GPU (small model)**: 5-20ms
- **GPU (large model)**: 10-50ms

### Factors Affecting Latency

**Model Size:**
- Small (384-dim): Faster
- Large (1536-dim): Slower
- Relationship roughly linear

**Input Length:**
- Short text (<100 tokens): Fast
- Long text (>512 tokens): Slower
- Often linear with token count

**Batch Size:**
- Single request: Higher per-item latency
- Batched (10-100): Lower per-item latency
- Trade-off with total time

**Network:**
- API calls: +network latency
- Local: Near-zero network
- Geographic distance matters

**Load:**
- Peak times: Higher latency
- Rate limits: Potential delays
- Queue wait times

## Impact on RAG Pipelines

### Query Flow
```
1. User query arrives
2. Generate query embedding    ← 50-200ms
3. Vector search              ← 10-50ms
4. LLM generation             ← 500-3000ms
──────────────────────────────────────────
Total: 560-3250ms
```

Embedding often 5-20% of total latency.

### Document Indexing
```
1000 documents × 100ms = 100 seconds
Batch (100 at once) × 200ms = 2 seconds
```
Batching critical for bulk operations.

## Optimization Strategies

### Batching
Group multiple requests:
```python
# Slow: Individual requests
for text in texts:
    embedding = api.embed(text)  # 100ms each
    # Total: 100ms × n

# Fast: Batch request
embeddings = api.embed_batch(texts)  # 200ms total
# Amortized: 200ms / n
```

### Caching
Store frequently used embeddings:
```python
import functools

@functools.lru_cache(maxsize=10000)
def get_embedding(text):
    return api.embed(text)
```

Benefits:
- Zero latency for cached
- Reduced API costs
- Typical hit rate: 20-60%

### Async/Parallel
Non-blocking requests:
```python
import asyncio

async def embed_many(texts):
    tasks = [api.embed_async(text) for text in texts]
    return await asyncio.gather(*tasks)
```

### Smaller Models
Trade quality for speed:
- 384-dim instead of 1536-dim
- Potentially 2-4x faster
- Test quality impact first

### Local Inference
Self-host for control:
- GPU: 5-50ms
- No network latency
- No API rate limits
- Higher upfront cost

### Precomputation
Embed documents offline:
- User queries only need embedding
- Document embeddings pre-cached
- Major latency reduction

## Monitoring

### Key Metrics
- P50, P95, P99 latency
- Error rates
- Throughput (embeddings/second)
- Queue depth

### Alerting
Set thresholds:
- P95 > 500ms: Warning
- P99 > 1000ms: Critical
- Error rate > 1%: Alert

### Tools
- Application Performance Monitoring (APM)
- Custom logging
- Provider dashboards
- Grafana/Prometheus

## Cost Considerations

### API Pricing
Typically per 1000 tokens:
- OpenAI: $0.0001-0.00013
- Cohere: $0.0001
- Voyage: $0.00012

### Self-Hosted
- GPU instance: $1-5/hour
- Break-even: Varies by usage
- Consider maintenance costs

## Best Practices

1. **Batch Aggressively**: Especially for indexing
2. **Cache Strategically**: High-value, frequent queries
3. **Precompute Documents**: Embed offline when possible
4. **Monitor Closely**: Track latency percentiles
5. **Set Timeouts**: Fail gracefully
6. **Use Async**: For multiple concurrent requests
7. **Test Models**: Balance speed vs quality
8. **Plan Capacity**: Understand peak loads

## Latency Budgets

Typical targets:
- **Interactive search**: <500ms total
- **Chatbots**: <2s total
- **Batch processing**: <10s per item
- **Background indexing**: Best effort

Allocate embedding budget accordingly.

## Pricing

API costs scale with volume; self-hosting has fixed infrastructure costs.