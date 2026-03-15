## Overview

The Hamming distance is a metric that compares two numeric vectors and computes how many changes are needed to convert one vector to the other. It counts the number of dimensions that differ between two vectors.

## Definition

For two vectors of equal length, the Hamming distance is the number of positions at which the corresponding elements are different.

## Use in Vector Search

- **Binary Quantization**: Primary distance metric for binary vectors
- **Categorical Data**: Comparing discrete values
- **Error Detection**: Measuring differences in encoded data
- **Efficient Computation**: Simple bitwise operations for binary vectors

## Example

Vector A: [1, 0, 1, 1, 0]
Vector B: [1, 1, 1, 0, 0]
Hamming Distance: 2 (positions 2 and 4 differ)

## Advantages

- Extremely fast computation for binary vectors using XOR operations
- Natural fit for binary quantized embeddings
- Memory efficient
- Simple to understand and implement

## Applications in Vector Databases

- Binary vector search with 32x memory compression
- Fast similarity search on quantized embeddings
- Categorical feature matching
- Deduplication and fuzzy matching

## Comparison with Other Metrics

Unlike Euclidean or cosine distance, Hamming distance works on discrete values and is particularly efficient for binary data where each comparison is a single CPU instruction.

## Pricing

Not applicable (mathematical concept).