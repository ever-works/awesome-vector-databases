## Overview

Starting from Qdrant v1.15.0, two additional quantization types were introduced: 1.5-bit and 2-bit binary quantization, which provide a useful middle ground between scalar and binary quantization.

## Benefits

- More aggressive compression than scalar quantization (4x)
- Better precision than standard binary quantization (32x)
- Useful middle ground for balancing memory and accuracy
- Enables larger datasets on the same hardware

## Technical Details

1.5-bit quantization uses 1.5 bits per dimension on average, achieved through clever encoding schemes that allow more precision than pure binary while maintaining high compression.

## Performance Characteristics

- Memory usage: ~10.7x compression vs float32
- Speed: Faster than scalar, slower than binary
- Accuracy: Better than binary, less than scalar
- Ideal for: Medium-scale deployments balancing cost and quality

## Use Cases

- Cost-sensitive deployments
- Large vector datasets (100M+ vectors)
- Applications tolerating slight accuracy trade-offs
- Memory-constrained environments

## Pricing

Included in Qdrant v1.15.0+, open-source.