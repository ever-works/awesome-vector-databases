## Overview

PaCMAP (Pairwise Controlled Manifold Approximation) is a dimensionality reduction method that preserves local and global structure through careful control of pair selection during optimization.

## Key Innovation

Three types of point pairs:
- **Near pairs**: Preserve local structure
- **Mid-near pairs**: Maintain global structure
- **Further pairs**: Prevent collapse

## Advantages

**Better Structure Preservation**:
- Superior global structure vs. t-SNE
- Better local structure vs. UMAP
- Balanced representation

**Stability**:
- More robust to hyperparameters
- Consistent results
- Less tuning required

**Speed**:
- Competitive with UMAP
- Faster than t-SNE
- Scales well

## Use Cases

- Embedding space visualization
- Quality assessment for vector models
- Cluster analysis
- Anomaly detection
- Interactive exploration

## Comparison

- vs. t-SNE: Better global structure, faster
- vs. UMAP: Better balance, more stable
- vs. PCA: Non-linear, preserves structure

## Availability

Python package: pacmap on PyPI

GitHub: YingfanWang/PaCMAP