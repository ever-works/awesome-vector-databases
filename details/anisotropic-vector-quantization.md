## Overview

Anisotropic Vector Quantization is an innovative compression technique introduced by Google Research in ScaNN (Scalable Nearest Neighbors). Unlike traditional quantization that minimizes overall distance, it prioritizes preserving parallel components between vectors.

## Key Innovation

Traditional quantization focuses on minimizing the overall distance between original and compressed vectors, which isn't ideal for Maximum Inner Product Search (MIPS). Anisotropic quantization instead preserves the components of vectors that are parallel to each other, which is crucial for inner product calculations.

## How It Works

1. Decomposes quantization error into parallel and orthogonal components relative to the query vector
2. Minimizes the parallel component of the error
3. Allows larger orthogonal errors that don't affect inner product scores
4. Results in more accurate similarity rankings

## Advantages

- **Higher Accuracy**: Better preservation of ranking order in MIPS tasks
- **Efficient Compression**: Achieves strong compression while maintaining quality
- **Optimized for Inner Products**: Specifically designed for dot product similarity
- **Proven Performance**: ScaNN handles ~2x queries per second vs. alternatives at the same accuracy

## Mathematical Foundation

For query vector q and database vector x, anisotropic quantization minimizes:
||q - q̂||² where q̂ is the quantized vector

But prioritizes minimizing the parallel component:
||(q - q̂) · x/||x|| ||²

## Use Cases

- Large-scale recommendation systems
- Neural search applications
- Image retrieval
- Document similarity with learned embeddings
- Any application using inner product or cosine similarity

## Implementation

Available in Google's ScaNN library as the default quantization method.

## Pricing

Free as part of open-source ScaNN library.