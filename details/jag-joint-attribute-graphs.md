## Overview

JAG (Joint Attribute Graphs) is a 2026 research paper that tackles filtered nearest neighbor search—a critical challenge where vector similarity search must be combined with attribute constraints (e.g., "find similar products that are in stock and under $50").

## Problem Statement

Traditional ANN indexes optimize for pure similarity search but struggle when queries include metadata filters. Common approaches either:
- Filter first, then search (inefficient with selective filters)
- Search first, then filter (inefficient with restrictive filters)
- Maintain separate indexes (expensive and difficult to synchronize)

## Key Contribution

JAG proposes a unified graph-based index structure that jointly models:
- Vector similarity relationships
- Attribute-based constraints
- The interaction between similarity and filtering

The approach builds graph connections that are aware of both vector proximity and attribute values, enabling efficient traversal that respects filter conditions.

## Technical Approach

The paper introduces:
- **Joint Graph Construction**: Builds proximity graphs that incorporate attribute information during construction
- **Filter-Aware Routing**: Graph traversal strategies that efficiently navigate to satisfy both similarity and filter criteria
- **Adaptive Indexing**: Adjusts graph structure based on common filter patterns

## Use Cases

- E-commerce product search (similarity + price/category/availability filters)
- Content recommendation with constraints (similar videos + duration/language/rating)
- Document retrieval with metadata (semantic search + date/author/department)
- Multi-modal search with attributes (image search + brand/color/size)

## Significance

Filtered vector search is increasingly important as real-world applications require combining semantic similarity with business logic and metadata constraints. JAG represents advancement in making this combination efficient at scale.

## Publication

Published as arXiv preprint arXiv:2602.10258 (2026) by Xu, Haike, et al.