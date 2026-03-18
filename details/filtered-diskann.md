## Overview

Filtered-DiskANN is a Microsoft Research extension to the DiskANN algorithm that enables efficient vector similarity search combined with label-based filtering, maintaining high performance even with complex filter conditions.

## Key Innovation

Traditional approaches either apply filters before search (reducing candidate pool) or after search (missing relevant results). Filtered-DiskANN integrates filtering directly into the graph traversal process.

## Features

- **Native Filter Integration**: Filters applied during graph traversal, not as pre/post-processing
- **Multiple Label Support**: Handle multiple filter labels per vector
- **Maintained Performance**: Minimal performance degradation with filters
- **Guaranteed Accuracy**: Ensures recall targets even with restrictive filters

## Use Cases

- E-commerce search with category/price filters
- Document search with access control
- Multi-tenant vector databases
- Personalized recommendations with user constraints
- Time-based vector retrieval

## Performance Characteristics

Compared to post-filtering approaches:
- Better recall at same latency
- More efficient for highly selective filters
- Reduced memory access patterns

## Implementation

Implemented in:
- pgvectorscale (Timescale)
- Microsoft's DiskANN library

## Research Impact

Published research has influenced modern vector database implementations, enabling practical filtered search at billion-scale.

## Pricing

Research paper - free to access.