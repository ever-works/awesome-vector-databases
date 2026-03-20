## Overview

Published in March 2025 (arXiv:2503.06882) and in VLDB 2025, this paper establishes an important theoretical connection between MIPS and nearest neighbor search through query scaling.

## Theoretical Contribution

The paper proves that Maximum Inner Product Search is equivalent to query-scaled nearest neighbor search under certain transformations. This connection:
- Provides theoretical foundation for MIPS algorithms
- Enables applying NN techniques to MIPS problems
- Offers performance guarantees
- Guides algorithm design

## Practical Implications

### Algorithm Design
NN algorithm advances can be adapted for MIPS with theoretical backing

### Index Structures
NN index structures (HNSW, IVF) can be used for MIPS with appropriate transformations

### Performance Analysis
NN theoretical results transfer to MIPS domain

## MIPS Applications Benefiting

- Recommendation systems at scale
- Neural network attention mechanisms
- Embedding-based retrieval
- Matrix completion
- Collaborative filtering

## Bridging Two Communities

The paper bridges:
- **ANN Research**: Decades of algorithms and theory
- **MIPS Applications**: Practical problems in ML and IR

This connection accelerates MIPS algorithm development by leveraging NN research.

## Technical Details

The query-scaled transformation:
- Modifies query vectors based on norm
- Preserves ranking (top-K results unchanged)
- Enables using distance-based indexes
- Maintains theoretical guarantees

## Impact on Vector Databases

Vector databases can now:
- Support both NN and MIPS with unified infrastructure
- Apply optimizations from NN domain to MIPS
- Provide theoretical performance guarantees for both

## Availability

Published as arXiv preprint arXiv:2503.06882 (2025) and PVLDB Vol. 18, with full theoretical proofs and experimental validation.