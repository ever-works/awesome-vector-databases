## Overview

Consistency levels in vector databases determine how fresh the data must be when reading. This is crucial in distributed systems with replication where writes may not instantly propagate to all replicas.

## Common Levels

### Strong
- Reads always return latest writes
- Highest latency
- Best for critical data

### Bounded Staleness
- Data may be slightly old (e.g., < 5 seconds)
- Better performance
- Still reasonably fresh

### Session
- Consistent within a session
- Different sessions may see different data
- Good balance

### Eventual
- Lowest latency
- Data will eventually be consistent
- Best for high-throughput reads

## Use Cases

**Strong**: Financial transactions, critical updates
**Bounded**: Real-time dashboards
**Session**: User-specific applications
**Eventual**: Analytics, batch processing

## Example (Milvus)

```python
results = collection.search(
    data=query_vectors,
    anns_field="embedding",
    param=search_params,
    limit=10,
    consistency_level="Eventually"  # Trade consistency for speed
)
```

## Trade-offs

- Strong: Slowest but most accurate
- Eventual: Fastest but may miss recent writes

## Pricing

Not applicable (configuration option).