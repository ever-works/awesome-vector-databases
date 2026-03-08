## Overview

Hierarchical Clustering-based Nearest Neighbor Graph (HCNNG) uses MST (Minimum Spanning Tree) to connect the points on dataset, dividing the dataset through multiple hierarchical clusters, with all points in each cluster connected through MST.

## Key Features

### Graph Construction
- Uses multiple global KD-trees to get seeds (similar to SPTAG and EFANNA)
- Divides dataset into hierarchical clusters
- Connects all points within each cluster through MST
- Creates hierarchical structure for efficient navigation

### Search Algorithm
- Performs efficient guided search instead of traditional greedy search
- Improves search efficiency through hierarchical cluster navigation
- Leverages cluster structure to reduce search space

## Comparison with Other Methods

State-of-the-art graph-based methods including KGraph, EFANNA, HNSW, DPG, NSG, SPTAG, SSG, Vamana, HCNNG, and ELPIS use the same search algorithm but differ in:
- How they construct the graph
- How they select seed points
- The structure of the resulting graph

## Technical Approach

HCNNG combines:
1. Hierarchical clustering for dataset organization
2. MST for intra-cluster connectivity
3. Guided search for efficient query processing
4. Global KD-trees for seed selection

## Applications

Suitable for:
- Large-scale approximate nearest neighbor search
- Datasets with natural cluster structure
- Applications requiring hierarchical organization
- Search systems needing guided routing