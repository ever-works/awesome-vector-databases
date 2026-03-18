## Why Benchmark?

- Compare database options
- Validate performance claims
- Capacity planning
- Regression detection
- Optimization validation

## Standard Benchmarks

**ANN-Benchmarks**:
- Industry standard
- Multiple datasets (SIFT, GIST, etc.)
- Reproducible methodology
- Public leaderboard
- Github: erikbern/ann-benchmarks

**VectorDBBench** (Zilliz):
- End-to-end workflows
- Real-world scenarios
- Multiple cloud providers
- Open-source

**MyScale VDB Benchmark**:
- Filtered search focus
- Cost comparisons
- Performance/cost trade-offs

## Key Metrics

### Performance

**Query Latency**:
- p50, p95, p99
- Different K values
- With/without filters

**Throughput**:
- QPS (queries per second)
- Concurrent queries
- Sustained load

**Index Build Time**:
- Initial creation
- Incremental updates
- Rebuild time

**Recall**:
- Accuracy of ANN
- At different ef_search values
- Trade-off with speed

### Resource Usage

**Memory**: Peak and average
**CPU**: Utilization
**Disk I/O**: Read/write patterns
**Network**: Bandwidth requirements

## Benchmarking Methodology

### 1. Dataset Selection

**Standard Datasets**:
- SIFT1M (1M 128-dim vectors)
- GIST1M (1M 960-dim vectors)
- DEEP1B (1B 96-dim vectors)
- Custom domain data

**Choose Based On**:
- Similar to production
- Representative size
- Appropriate dimensions

### 2. Test Scenarios

**Baseline**:
- Pure vector search
- No filters
- Single client

**Filtered Search**:
- With metadata filters
- Various selectivity
- Critical for production

**Concurrent Load**:
- Multiple clients
- Realistic concurrency
- Identify bottlenecks

**Mixed Workload**:
- Reads + writes
- Updates
- Deletes

### 3. Configuration Testing

**Index Parameters**:
- HNSW: M, ef_construction
- IVF: nlist, nprobe
- Compare configurations

**Query Parameters**:
- top-K values
- ef_search settings
- Batch sizes

### 4. Measurement

**Warm-up**:
- Run queries to warm cache
- Exclude from results
- 100-1000 queries typical

**Measurement Period**:
- Long enough for stability
- 5000+ queries minimum
- Multiple runs

**Statistical Analysis**:
- Mean and percentiles
- Standard deviation
- Confidence intervals

## Benchmarking Script Example

```python
import time
import numpy as np

def benchmark_queries(db, queries, k=10, warmup=100):
    # Warm-up
    for q in queries[:warmup]:
        db.search(q, k)
    
    # Measure
    latencies = []
    for q in queries[warmup:]:
        start = time.perf_counter()
        results = db.search(q, k)
        latencies.append(time.perf_counter() - start)
    
    # Analyze
    return {
        'p50': np.percentile(latencies, 50),
        'p95': np.percentile(latencies, 95),
        'p99': np.percentile(latencies, 99),
        'mean': np.mean(latencies),
        'qps': len(latencies) / sum(latencies)
    }
```

## Recall Calculation

```python
def calculate_recall(approx_results, exact_results, k):
    """Calculate recall@k"""
    correct = len(set(approx_results[:k]) & set(exact_results[:k]))
    return correct / k
```

## Cloud vs Self-Hosted

**Cloud Considerations**:
- Network latency
- Instance types
- Regional differences
- Pricing tiers

**Self-Hosted**:
- Hardware specs
- Network configuration
- OS and tuning
- Consistent environment

## Reporting Results

**Include**:
- Dataset characteristics
- Hardware/cloud specs
- Software versions
- Configuration used
- Warm-up details
- Statistical measures
- Reproducibility info

**Visualize**:
- Latency histograms
- Throughput over time
- Recall vs QPS trade-off
- Cost per query

## Common Pitfalls

1. **Cold Start**: Not warming up
2. **Too Short**: Insufficient queries
3. **Wrong Dataset**: Not representative
4. **Single Run**: No statistical validity
5. **Ignoring Variance**: Network/system noise
6. **Unrealistic Load**: Single-threaded only
7. **Missing Filters**: Production has them
8. **Cache Effects**: Not accounting for

## Best Practices

1. **Use Realistic Data**: Match production
2. **Test Multiple Scenarios**: Don't just baseline
3. **Multiple Runs**: Get statistical confidence
4. **Document Everything**: Reproducibility
5. **Compare Fairly**: Same hardware/dataset
6. **Test at Scale**: Production size
7. **Include Filters**: Real-world usage
8. **Monitor Resources**: Full picture
9. **Test Failures**: Error conditions
10. **Continuous Benchmarking**: Detect regressions

## Vendor Claims Validation

**Be Skeptical**:
- Reproduce independently
- Check test conditions
- Look for caveats
- Test your workload

**Red Flags**:
- No methodology details
- Cherry-picked scenarios
- Unrealistic conditions
- Missing recall metrics

## Cost-Performance Analysis

**Calculate**:
```
Cost per 1M queries = 
    (instance_cost/hour * query_time_hours) / 1M queries
```

**Compare**:
- Different databases
- Different configs
- Different instance types
- Find sweet spot

## Continuous Benchmarking

**Setup**:
- Automated nightly runs
- Track over time
- Alert on regressions
- Before/after deploys

**Tools**:
- Custom scripts
- CI/CD integration
- Monitoring systems

## Resource Links

- ANN-Benchmarks: github.com/erikbern/ann-benchmarks
- VectorDBBench: github.com/zilliztech/VectorDBBench
- MyScale Benchmark: myscale.github.io/benchmark