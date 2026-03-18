## Why Sharding?

As vector collections grow beyond single-node capacity, sharding distributes data across multiple nodes for:
- Horizontal scalability
- Parallel query processing
- Higher throughput
- Fault tolerance

## Sharding Strategies

**Hash-Based Sharding**:
- Hash vector ID to determine shard
- Even distribution
- Simple implementation
- Random data distribution

**Range-Based Sharding**:
- Partition by ID ranges
- Sequential data grouped together
- Can lead to hot spots
- Good for time-series data

**Semantic Sharding**:
- Cluster similar vectors together
- Reduces cross-shard queries
- More complex
- Better query performance

**Hybrid Approach**:
- Combine semantic clustering with hash
- Balance distribution and locality

## Query Routing

**Broadcast**:
- Query all shards
- Merge results
- Simple but inefficient

**Selective Routing**:
- Route to relevant shards only
- Requires metadata/clustering
- More efficient

**Hierarchical**:
- Query coordinator → shard leaders → replicas
- Better for large clusters

## Replication

**Why Replicate**:
- High availability
- Read scalability
- Disaster recovery

**Strategies**:
- Master-slave: One writer, multiple readers
- Multi-master: Multiple writers (complex)
- Typical: 2-3 replicas

## Rebalancing

**When Needed**:
- Adding/removing nodes
- Uneven shard sizes
- Hot spot detection

**Approaches**:
- Background data movement
- Virtual shards (easier rebalancing)
- Consistent hashing

## Database Support

**Native Sharding**:
- Milvus (automatic sharding)
- Weaviate (horizontal scaling)
- Qdrant (distributed mode)
- Vespa (native distribution)

**Manual Sharding**:
- Multiple Pinecone indexes
- Multiple Chroma collections
- Application-level routing

## Best Practices

1. Plan for growth (don't shard too early)
2. Use consistent hashing
3. Monitor shard balance
4. Implement health checks
5. Test failure scenarios
6. Have rebalancing strategy
7. Consider network topology
8. Monitor cross-shard queries

## Performance Considerations

- Cross-shard queries add latency
- Network bandwidth important
- Replication increases write cost
- Balance parallelism vs overhead

## When to Shard

**Don't shard if**:
- < 50M vectors
- Single node handles load
- Simplicity preferred

**Consider sharding if**:
- > 100M vectors
- Need higher throughput
- Geographic distribution
- Regulatory requirements