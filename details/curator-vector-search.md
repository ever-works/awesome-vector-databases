## Overview

Curator presents efficient indexing techniques for multi-tenant vector databases, specifically addressing the challenge of low-selectivity filters—queries where filter conditions match only a small fraction of the dataset.

## Problem Context

In multi-tenant vector database deployments:
- Each tenant's data is isolated but stored in the same physical database
- Queries must combine similarity search with tenant ID filters
- Low-selectivity filters (e.g., single tenant out of thousands) create performance challenges
- Traditional approaches either scan too much data or maintain expensive per-tenant indexes

## Key Innovation

Curator proposes indexing strategies that:
- Efficiently handle both high and low selectivity filters
- Avoid the overhead of maintaining separate indexes per tenant
- Optimize for the common case of single-tenant queries
- Scale to large numbers of tenants without linear cost growth

## Technical Contributions

**Efficient Filter Integration**: Novel techniques for incorporating filter predicates into graph-based ANN indexes

**Adaptive Routing**: Graph traversal strategies that quickly navigate to relevant filtered regions

**Space-Time Tradeoffs**: Methods to balance index size, query latency, and filter selectivity

## Use Cases

- SaaS vector databases serving thousands of customers
- Enterprise AI platforms with departmental isolation
- Multi-application vector stores with namespace filtering
- Cloud vector database services with tenant isolation requirements

## Performance Benefits

The paper demonstrates:
- Efficient handling of queries with varying filter selectivity
- Reduced index overhead compared to per-tenant approaches
- Improved query latency for low-selectivity filtered searches
- Better resource utilization in multi-tenant deployments

## Availability

Published as arXiv preprint arXiv:2401.07119 (2024) by Jin, Yicheng, et al. The work addresses an increasingly important problem as vector databases move to production multi-tenant deployments.