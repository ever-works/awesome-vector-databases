## Overview

Progressive K-Annealing is a training technique used in CSRv2 that stabilizes sparsity learning by gradually increasing the sparsity constraint (reducing k) during training.

## How It Works

Instead of starting with ultra-sparse representations (k=2 or k=4), the training begins with higher k values and progressively reduces k over the training process. This allows the model to first learn good dense representations before being compressed.

## Benefits

- Reduces dead neurons from >80% to ~20%
- Delivers 14% accuracy gain at k=2 compared to prior methods
- Enables stable training of ultra-sparse embeddings
- Improves final model quality

## Technical Details

The annealing schedule typically:
1. Starts with k=64 or k=128
2. Gradually reduces to target k (e.g., k=2 or k=4)
3. Uses smooth transitions to avoid training instability
4. Combines with supervised contrastive objectives

## Results

CSRv2 with progressive k-annealing achieves up to 300x improvements in compute and memory efficiency relative to dense embeddings and 7x speedup over Matryoshka Representation Learning.

## Pricing

Research technique, open-source implementation.