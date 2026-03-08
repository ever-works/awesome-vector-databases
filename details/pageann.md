## Overview

PageANN is a disk-based approximate nearest neighbor search (ANNS) framework designed for high performance and scalability. The framework enables efficient large-scale ANN search under various memory budgets while maintaining high recall accuracy.

## Key Innovation

PageANN introduces a page-node graph structure that aligns logical graph nodes with physical SSD pages, where similar vectors are clustered into page nodes. This mapping ensures that each visited graph node corresponds to a single SSD page read.

## Technical Approach

- Co-designed disk data layout leverages page-node structure
- Merging technique stores only representative vectors and topology information
- Avoids unnecessary reads through intelligent data organization
- Memory management strategy combines lightweight indexing with coordinated memory-disk allocation

## Performance Results

Experimental results demonstrate significant advantages:
- 1.85x-10.83x higher throughput vs. state-of-the-art disk-based ANNS methods
- 51.7%-91.9% lower latency across different datasets and memory budgets
- Maintains comparable high recall accuracy
- Reduces random I/O through page-level graph organization
- Improves SSD utilization during vector search

## Research

Published on arXiv (2509.25487) in late 2025. PageANN extends Microsoft's DiskANN with page-level graph organization.

## Availability

Source code available on GitHub.