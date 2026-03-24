## Overview

Co-partitioned Vector Index is an indexing strategy where vector indexes are stored in the same database partitions/tablets as the corresponding table rows, ensuring tight data locality.

## Architecture

In a co-partitioned layout:
1. Table rows and their vector indexes live together
2. No cross-partition lookups needed
3. Updates are transactional within a single partition
4. Queries benefit from data locality

## Benefits

- **Data Locality**: Vectors and metadata are physically close
- **Performance**: Reduced network hops for queries
- **Consistency**: Easier to maintain ACID properties
- **Scalability**: Horizontal scaling without coordination overhead
- **Operational Simplicity**: Unified backup and recovery

## Comparison to Alternatives

### Separate Vector Store
- Requires cross-system joins
- Complex consistency management
- Higher latency

### Global Vector Index
- Single point of bottleneck
- Difficult to scale
- Higher operational complexity

## Implementation

YugabyteDB uses co-partitioned vector indexes as part of its Vector LSM architecture, enabling billion-vector scale with sub-second latency.

## Use Cases

- Distributed SQL databases with vector support
- Multi-tenant applications
- Geo-distributed systems
- Large-scale production deployments

## Pricing

Architectural pattern, used in YugabyteDB and similar distributed databases.