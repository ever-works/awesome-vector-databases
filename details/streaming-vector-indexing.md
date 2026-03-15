## Overview

Streaming vector indexing processes vectors incrementally as they arrive, making them immediately searchable without waiting for batch jobs. Essential for real-time applications.

## Batch vs Streaming

### Batch Indexing
- Collect vectors
- Build index periodically (hourly/daily)
- High latency (hours)
- Better index quality

### Streaming Indexing
- Index each vector on arrival
- Immediate searchability (seconds)
- Slightly degraded index quality
- Continuous updates

## Implementation Patterns

### Dual-Index Strategy
```python
# Recent vectors: in-memory, immediately searchable
recent_index.add(new_vector)

# Older vectors: optimized disk index
if time_to_merge:
    optimized_index.merge(recent_index)
    recent_index.clear()

# Search both
results = search([recent_index, optimized_index], query)
```

### Delta Index
- Main index: batch-built, optimized
- Delta index: streaming, fast insertion
- Periodic merge to main

## Challenges

- Index quality degradation
- Resource overhead
- Merge complexity
- Consistency during merges

## Use Cases

- Social media feeds
- News recommendation
- Real-time monitoring
- Fraud detection
- Live event search

## Database Support

- **Milvus**: Streaming updates with growing segments
- **Pinecone**: Real-time upserts
- **Weaviate**: Immediate indexing
- **Qdrant**: Online indexing

## Best Practices

1. Use dual-index for best quality + freshness
2. Monitor index quality metrics
3. Schedule periodic rebuilds
4. Test merge strategies
5. Benchmark search latency

## Pricing

Higher resource usage than batch; varies by database.