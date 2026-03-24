## Overview

Supervised Contrastive Objectives are training techniques used in CSRv2 to improve the quality of ultra-sparse embeddings by leveraging labeled training data.

## How It Works

Instead of relying solely on unsupervised contrastive learning, supervised contrastive objectives:
1. Use class labels to define positive and negative pairs
2. Pull together embeddings from the same class
3. Push apart embeddings from different classes
4. Maintain this structure even at extreme sparsity levels

## Benefits

- Better class separation in embedding space
- Improved accuracy at ultra-sparse dimensions (k=2, k=4)
- More stable training process
- Better generalization to downstream tasks

## Combined with Progressive K-Annealing

When combined with progressive k-annealing, supervised contrastive objectives enable CSRv2 to achieve 14% accuracy gains at k=2 compared to prior methods.

## Applications

- Classification tasks
- Retrieval systems
- Few-shot learning
- Transfer learning

## Research Impact

This technique is part of CSRv2's breakthrough in making ultra-sparse embeddings practical, achieving up to 300x improvements in compute and memory efficiency.

## Pricing

Research technique, open-source.