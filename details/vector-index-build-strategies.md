## Overview

Index build strategies determine how vector indexes are constructed and maintained, with trade-offs between build time, search quality, and resource usage.

## Build Approaches

### Batch Build
- Build index from scratch with all data
- Optimized index quality
- Requires downtime or dual-indexing
- Best for periodic rebuilds

### Incremental Build
- Add vectors to existing index
- No downtime
- May degrade index quality over time
- Periodic rebuilds recommended

### Online Indexing
- Index updates in real-time
- Immediate searchability
- Higher resource overhead
- Complex coordination

## Optimization Techniques

### GPU Acceleration
```python
# Milvus with GPU
index_params = {
    "index_type": "GPU_IVF_PQ",
    "metric_type": "L2",
    "params": {"nlist": 1024}
}
```
- 10-100x faster build
- Requires GPU resources
- Not all algorithms supported

### Parallel Construction
- Distribute build across cores
- Linear speedup with cores
- Memory intensive

### Sampling for Parameters
- Use subset to determine optimal parameters
- Much faster than full-data optimization
- Representative sample is key

## Best Practices

1. **Initial Build**: Use batch with optimization
2. **Updates**: Incremental up to threshold
3. **Rebuild**: Periodic (weekly/monthly)
4. **Monitoring**: Track index quality metrics
5. **Testing**: Validate search quality after builds

## Resource Planning

**CPU**: 8-16 cores for parallel build
**Memory**: 2-3x vector data size
**GPU**: Optional, 10-100x speedup
**Time**: Hours for billions of vectors

## Pricing

Resource costs during build; varies by strategy and scale.