## Overview

Manhattan distance (L1 norm) calculates the distance between vectors by summing the absolute differences of their components. Also known as taxicab or city block distance.

## Formula

Distance = Σ|a[i] - b[i]|

## Characteristics

- **Grid Distance**: Measures path along axes (like Manhattan city blocks)
- **Outlier Robust**: Less sensitive to outliers than Euclidean
- **Fast Computation**: Values typically smaller than Euclidean
- **High-Dimensional Friendly**: Better performance as dimensions increase

## When to Use

- High-dimensional data
- When outliers are present
- Computational efficiency is important
- Grid-like or discrete data

## Performance Benefits

- Faster to calculate than Euclidean distance
- Values are typically smaller
- Recommended as dimensionality increases

## Comparison

- **Manhattan**: Grid distance, robust to outliers
- **Euclidean**: Straight-line distance, sensitive to outliers
- **Cosine**: Angular similarity, scale invariant

## Use Cases

- High-dimensional feature spaces
- Data with potential outliers
- Performance-sensitive applications
- Discrete or grid-structured data

## Limitations

Less intuitive than Euclidean distance for geometric problems. May not reflect actual similarity for normalized or angular comparisons.

## Vector Database Support

Supported by some vector databases, though less common than cosine and Euclidean. Check specific database documentation.