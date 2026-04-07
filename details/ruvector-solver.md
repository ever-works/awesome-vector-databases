## Overview

Solves problems faster as data grows, powering real-time self-learning.

## Algorithms

| Algorithm | Complexity | Best For |
|-|-|-|
| Neumann Series | O(k · nnz) | Diagonally dominant |
| Conjugate Gradient | O(√κ · log(1/ε) · nnz) | SPD systems |
| Forward Push | O(1/ε) | Single-source PageRank |
| Backward Push | O(1/ε) | Reverse relevance |
| Hybrid Random Walk | O(√n/ε) | Pairwise relevance |
| TRUE | O(log n) amortized | Laplacian systems |
| BMSSP | O(nnz · log n) | Multigrid solve |
| Auto Router | Automatic | Optimal selection |

Key optimizations: AVX2 SIMD, fused residuals, bounds-check elimination.

## Installation

```sh
cargo add ruvector-solver --features all-algorithms
```

## Pricing

Free and open-source.