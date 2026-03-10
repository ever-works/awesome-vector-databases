## Overview

Scalar quantization strikes an excellent balance between compression and performance, compressing 32-bit floating-point values into 8-bit unsigned integers, reducing memory usage by 75%.

## How It Works

1. Find min and max values in vector components
2. Map range [min, max] to [0, 255]
3. Convert each float32 to uint8
4. Store quantized vectors
5. Dequantize during search if needed

## Benefits

- **75% Memory Reduction**: From 32 bits to 8 bits per component
- **Faster Processing**: Smaller data fits better in cache
- **Good Accuracy**: Minimal quality loss compared to full precision
- **Simple Implementation**: Straightforward conversion process
- **Wide Support**: Available in most vector databases

## Performance Characteristics

- Minimal accuracy loss (typically <2%)
- Significant memory savings
- Improved query throughput
- Better cache utilization
- Reduced bandwidth requirements

## Comparison with Other Techniques

- **vs. Binary Quantization**: Less aggressive, better accuracy
- **vs. Product Quantization**: Simpler, faster, less compression
- **vs. No Quantization**: 75% less memory, slightly lower accuracy

## Use Cases

- Large-scale vector databases
- Memory-constrained environments
- Production deployments
- Cost optimization
- High-throughput applications

## Implementation Considerations

- Apply during indexing or online
- Monitor accuracy metrics
- Combine with proper monitoring
- Consider per-vector or global ranges
- Test impact on your specific use case

## Best Practices (2026)

- Use for memory optimization in production
- Combine with other optimization techniques
- Monitor for accuracy regressions
- Benchmark against your data
- Consider as first quantization step

## Database Support

- Qdrant (native support)
- Milvus
- Weaviate
- Pinecone
- Most modern vector databases

## When to Use

- Need significant memory reduction
- Can tolerate minimal accuracy loss
- Production systems requiring optimization
- Large-scale deployments
- Budget-conscious applications