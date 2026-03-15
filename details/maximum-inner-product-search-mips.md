## Overview

Maximum Inner Product Search (MIPS) is the problem of finding vectors in a database that maximize the inner product with a query vector. Unlike nearest neighbor search, MIPS considers both direction and magnitude, making it ideal for applications where vector magnitude has semantic meaning.

## Problem Definition

Given query vector q and database D, find:
argmax_{x ∈ D} (q · x)

Where · represents the inner product (dot product).

## Why MIPS Matters

- **Magnitude Significance**: In many applications, larger magnitude indicates higher relevance or confidence
- **Recommendation Systems**: User-item affinity scores naturally fit MIPS
- **Neural Networks**: Many models are trained to maximize inner products
- **Asymmetric Similarity**: Query and database vectors may have different interpretations

## Difference from ANN

**ANN (Approximate Nearest Neighbor)**: Finds vectors with minimum distance
**MIPS**: Finds vectors with maximum inner product

MIPS is **not** equivalent to ANN in general, requiring specialized algorithms.

## Specialized Techniques

### Anisotropic Vector Quantization
Introduced by Google's ScaNN, this technique:
- Preserves parallel components between vectors
- Optimizes quantization specifically for inner product
- Significantly improves MIPS accuracy

### Transformation Methods
Some approaches transform MIPS to ANN:
- Add extra dimensions to vectors
- Apply transformations that convert max inner product to min distance

## Applications

- **Collaborative Filtering**: User-item recommendations
- **Neural Retrieval**: Document ranking with learned embeddings
- **Ad Targeting**: Matching ads to users
- **Content Recommendation**: Maximizing relevance scores
- **Multi-Armed Bandits**: Arm selection in reinforcement learning

## Algorithms Optimized for MIPS

- **ScaNN**: Google's library with anisotropic quantization
- **ALSH**: Asymmetric Locality-Sensitive Hashing
- **Modified IVF**: Adapted inverted file indexes
- **Specialized HNSW variants**: Graph methods adapted for inner product

## Challenges

- Traditional ANN methods may perform poorly on MIPS
- Quantization techniques designed for L2 distance don't transfer well
- Need to preserve ranking order, not just approximate values

## When to Use MIPS

- Embeddings where magnitude is meaningful (e.g., confidence, relevance)
- Models trained with inner product objectives
- Recommendation systems with explicit scoring
- When vectors are not normalized

## Performance Considerations

MIPS-optimized algorithms like ScaNN can handle ~2x more queries per second than general ANN approaches at the same accuracy level for inner product tasks.

## Pricing

Not applicable (search paradigm/algorithm class).