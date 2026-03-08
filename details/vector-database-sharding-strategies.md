## Overview

Vector databases support horizontal scaling through sharding, which distributes data across multiple nodes, and replication, which creates redundant copies for high availability.

## Key Sharding Strategies

### Range-Based Sharding
Partitions vector data across shards by dividing it into non-overlapping key intervals based on sorted keys.

**Advantages**:
- Simple to implement
- Efficient for range-based queries

**Disadvantages**:
- Data skew and uneven load distribution if keys not uniformly distributed

### Hash-Based Sharding
Uses 64-bit Murmur-3 hash algorithm based on each object's UUID to determine shard placement through a virtual shard system.

**Advantages**:
- Spreads data evenly across shards
- Predictable distribution

**Disadvantages**:
- Ignores semantic relationships
- Can scatter related vectors across shards

### Geographic Sharding
Distributes vector data based on geographic attributes (user region, location), assigning each shard to a specific geographic zone.

**Advantages**:
- Reduces cross-region network latency by storing data closer to users
- Helps comply with data sovereignty regulations

**Disadvantages**:
- Uneven load if users concentrated in certain regions

### Vector-Aware Sharding
Groups vectors into clusters using algorithms like k-means or HNSW, with each cluster assigned to a shard. Queries routed to the most relevant shards based on proximity to query vector.

**Advantages**:
- Maintains semantic relationships
- Reduces cross-shard queries
- Improved query efficiency

**Disadvantages**:
- Resource-intensive re-clustering when adding/removing vectors
- Complexity in maintaining cluster balance

## Query Execution Patterns

### Scatter-Gather
Queries are sent to all shards, and results are retrieved and combined. Each shard processes its portion of the index and returns local results, which are then merged and ranked.

### Selective Routing
Vector-aware sharding enables routing queries only to relevant shards, reducing network overhead.

## Challenges and Trade-offs

- **Accuracy**: Global nearest neighbors might reside in different shards
- **Latency**: Network overhead from querying multiple shards
- **Dynamic Updates**: Re-clustering is resource-intensive
- **Load Balancing**: Certain shards may grow faster, creating hotspots

## Sharding vs. Partitioning

Sharding focuses on distributing data across multiple machines for horizontal scalability, while partitioning primarily organizes data within a single machine for local optimization.

## Industry Adoption

By 2026, over 30% of enterprises are projected to integrate vector databases to support foundation models - up from less than 2% in 2023.