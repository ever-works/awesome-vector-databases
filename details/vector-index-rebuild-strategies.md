## Overview

Vector index rebuilds update the search structures (HNSW, IVF, etc.) to maintain performance as data changes. Proper rebuild strategies minimize downtime and ensure optimal search quality.

## When to Rebuild

### Triggers
- Large data additions (>10-20% growth)
- Significant deletions
- Index fragmentation
- Parameter tuning (M, ef_construction)
- Performance degradation
- Model/embedding changes

### Signs Rebuild Needed
- Query latency increasing
- Recall degrading
- Memory usage growing
- Index size bloated
- Fragmentation metrics high

## Rebuild Strategies

### Online Rebuild
**Approach**: Rebuild while serving traffic

**Process:**
1. Create new index structure
2. Migrate vectors incrementally
3. Dual-write to both indexes
4. Cutover when complete
5. Delete old index

**Advantages**: Zero downtime
**Disadvantages**: 2x resources temporarily

### Blue-Green Deployment
**Approach**: Two complete environments

**Process:**
1. Build new (green) index
2. Validate quality
3. Switch traffic to green
4. Keep blue as rollback
5. Delete blue after validation

**Advantages**: Safe, quick rollback
**Disadvantages**: 2x storage cost

### Scheduled Downtime
**Approach**: Maintenance window

**Process:**
1. Announce downtime
2. Stop writes
3. Rebuild index
4. Validate
5. Resume service

**Advantages**: Simple, clean
**Disadvantages**: Downtime required

### Incremental Updates
**Approach**: Continuous small rebuilds

**Process:**
- HNSW: Insert vectors directly
- IVF: Periodic re-clustering
- Batch small updates

**Advantages**: No large rebuilds
**Disadvantages**: Gradual performance decay

## Implementation Examples

### Zero-Downtime HNSW
```python
def online_rebuild_hnsw():
    # Create new index
    new_index = create_hnsw_index(
        M=32,  # Updated parameter
        ef_construction=200
    )
    
    # Dual write mode
    enable_dual_write(old_index, new_index)
    
    # Migrate existing vectors
    batch_size = 10000
    for batch in get_batches(old_index, batch_size):
        new_index.add(batch)
        log_progress()
    
    # Validate quality
    recall = validate_index(new_index)
    if recall < 0.95:
        rollback()
        return
    
    # Cutover
    switch_reads_to(new_index)
    
    # Cleanup
    wait_for_in_flight_queries()
    delete(old_index)
```

### Blue-Green with Validation
```python
def blue_green_rebuild():
    # Build green index
    green = build_index_from_scratch(
        vectors=get_all_vectors(),
        config=new_config
    )
    
    # Comprehensive testing
    test_results = run_test_suite(green)
    if not test_results.passed:
        delete(green)
        alert("Rebuild failed validation")
        return
    
    # Gradual cutover
    route_percentage(green, percent=10)
    monitor_metrics(duration_minutes=30)
    
    if metrics_acceptable():
        route_percentage(green, percent=100)
        mark_as_blue(current_index)
        delete(blue)  # Old index
    else:
        rollback_to_blue()
```

## Parameter Tuning

### HNSW Parameters
Common rebuild reasons:
```python
# Before
index = HNSW(M=16, ef_construction=100)

# After (better quality)
index = HNSW(M=32, ef_construction=200)
```

### IVF Parameters
```python
# Before
index = IVF(nlist=100)

# After (more clusters for larger dataset)
index = IVF(nlist=int(np.sqrt(num_vectors)))
```

## Validation Process

### Quality Checks
```python
def validate_rebuild(new_index, test_queries, ground_truth):
    recalls = []
    latencies = []
    
    for query, true_results in zip(test_queries, ground_truth):
        start = time.time()
        results = new_index.search(query, k=10)
        latency = time.time() - start
        
        recall = compute_recall(results, true_results)
        recalls.append(recall)
        latencies.append(latency)
    
    return {
        "recall_mean": np.mean(recalls),
        "recall_p95": np.percentile(recalls, 95),
        "latency_p50": np.percentile(latencies, 50),
        "latency_p95": np.percentile(latencies, 95),
        "passed": all(r >= 0.95 for r in recalls)
    }
```

## Monitoring Rebuild

### Progress Tracking
```python
def track_rebuild_progress():
    return {
        "vectors_migrated": count_migrated(),
        "total_vectors": count_total(),
        "progress_pct": (count_migrated() / count_total()) * 100,
        "estimated_time_remaining": estimate_remaining(),
        "current_qps": measure_qps(),
        "memory_usage_gb": get_memory_usage()
    }
```

### Metrics to Monitor
- Migration progress (%)
- Query latency (P50, P95, P99)
- Error rate
- Memory usage
- CPU usage
- Disk I/O

## Best Practices

1. **Test in Staging**: Validate rebuild process
2. **Gradual Cutover**: Route traffic incrementally
3. **Monitor Closely**: Watch all metrics
4. **Have Rollback Plan**: Quick revert if issues
5. **Communicate**: Notify stakeholders
6. **Off-Peak Hours**: When possible
7. **Resource Buffer**: Ensure adequate capacity
8. **Automate**: Script the process

## Common Pitfalls

### Insufficient Resources
- Need 2x memory during rebuild
- Provision adequately
- Monitor resource usage

### Incomplete Validation
- Test thoroughly before cutover
- Include edge cases
- Check all query types

### Rushed Cutover
- Give dual-mode time to stabilize
- Monitor metrics carefully
- Don't rush production switch

## Rollback Procedures

### Quick Rollback
```python
def emergency_rollback():
    # Immediate traffic switch
    route_all_traffic_to(blue_index)
    
    # Alert team
    send_alert("Rolled back from rebuild")
    
    # Investigate
    collect_logs()
    analyze_failure()
    
    # Cleanup failed rebuild
    delete(green_index)
```

## Pricing

Rebuild costs include temporary 2x resources and processing time.