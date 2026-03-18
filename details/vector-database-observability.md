## Why Observability Matters

Vector databases are critical infrastructure. Poor observability leads to undetected issues, degraded user experience, and difficult debugging.

## Three Pillars

**1. Metrics**: Quantitative measurements
**2. Logs**: Discrete events
**3. Traces**: Request flows

## Key Metrics to Track

### Query Performance

**Latency**:
- p50, p95, p99 query time
- Target: p95 < 100ms typical
- Alert: p95 > 500ms

**Throughput**:
- Queries per second (QPS)
- Track peak vs average
- Capacity planning

**Error Rate**:
- Failed queries / total
- Target: < 0.1%
- Alert: > 1%

### Retrieval Quality

**Recall@K**:
- Percentage of relevant results
- Monitor over time
- Alert on degradation

**Result Count**:
- Empty results rate
- Low result rate
- Distribution of result counts

### Resource Usage

**Memory**:
- Index size
- Query memory
- Cache usage
- Alert: > 85% capacity

**CPU**:
- Utilization %
- Query cost
- Indexing cost

**Disk I/O**:
- Read/write throughput
- Latency
- Queue depth

**Network**:
- Bandwidth usage
- Connection count
- Failed connections

### Index Health

**Build Time**: Index creation duration
**Index Size**: On disk and memory
**Fragmentation**: For dynamic indexes
**Update Lag**: For incremental updates

## Logging Strategy

**What to Log**:

**Query Logs**:
```json
{
  "timestamp": "2026-03-18T10:30:00Z",
  "query_id": "uuid",
  "query_text": "hashed or sample",
  "latency_ms": 45,
  "result_count": 10,
  "user_id": "hashed",
  "filters": {...},
  "status": "success"
}
```

**Error Logs**:
```json
{
  "timestamp": "2026-03-18T10:31:00Z",
  "error_type": "timeout",
  "query_id": "uuid",
  "message": "Query exceeded 1s timeout",
  "stack_trace": "..."
}
```

**System Logs**:
- Index builds/updates
- Configuration changes
- Scaling events
- Maintenance operations

## Distributed Tracing

**Full Request Flow**:
1. API gateway
2. Embedding service
3. Vector database query
4. Post-processing
5. LLM generation (if RAG)
6. Response return

**Tools**:
- OpenTelemetry
- Jaeger
- Zipkin
- DataDog APM

**Span Annotations**:
- Query parameters
- Result counts
- Cache hits/misses
- Cost tracking

## Alerting

**Critical Alerts** (immediate):
- Service down
- Error rate > 5%
- p99 latency > 5s
- Memory > 95%

**Warning Alerts** (15min):
- Error rate > 1%
- p95 latency > 2x baseline
- Disk > 85%
- Unusual query patterns

**Info Alerts** (daily):
- Capacity trending
- Cost anomalies
- Usage patterns

## Dashboards

**Executive Dashboard**:
- QPS over time
- Success rate
- p95 latency
- Cost per query
- User satisfaction

**Operations Dashboard**:
- Resource utilization
- Error breakdown
- Query patterns
- Index health
- Alert status

**Debug Dashboard**:
- Recent errors
- Slow queries
- Resource spikes
- Trace samples

## Debugging Techniques

**Slow Query Analysis**:
1. Identify slow queries
2. Check query complexity
3. Examine filter selectivity
4. Review index configuration
5. Check resource contention

**Error Investigation**:
1. Aggregate by error type
2. Find common patterns
3. Check recent changes
4. Review resource limits
5. Examine dependencies

**Quality Degradation**:
1. Compare to baseline
2. Check embedding model
3. Review index integrity
4. Test with known queries
5. Examine data changes

## Monitoring Tools

**Infrastructure**:
- Prometheus + Grafana
- DataDog
- New Relic
- CloudWatch (AWS)

**Vector DB Specific**:
- Database built-in metrics
- Vendor dashboards
- Custom exporters

**Application**:
- LangSmith
- Phoenix (Arize)
- TruLens

## Best Practices

1. **Baseline Everything**: Know normal
2. **Monitor Proactively**: Don't wait for issues
3. **Alert Wisely**: Avoid fatigue
4. **Log Strategically**: Balance detail vs volume
5. **Trace Critical Paths**: End-to-end visibility
6. **Dashboard for Audience**: Different views
7. **Review Regularly**: Weekly/monthly reviews
8. **Test Alerts**: Verify they fire
9. **Document Runbooks**: Link to dashboards
10. **Iterate**: Improve over time

## Cost Monitoring

**Track**:
- Compute costs
- Storage costs
- Network egress
- API calls (if managed service)

**Optimize**:
- Right-size resources
- Implement caching
- Use quantization
- Review query patterns

## SLIs and SLOs

**Example SLIs**:
- Availability: 99.9%
- p95 latency: < 100ms
- Error rate: < 0.1%

**Example SLOs**:
- 99.5% of queries < 100ms
- 99.9% uptime monthly
- < 0.5% error rate

## Common Issues Detected

- Memory leaks
- Slow queries
- Index corruption
- Resource exhaustion
- Configuration drift
- Dependency failures
- Network issues
- Capacity limits