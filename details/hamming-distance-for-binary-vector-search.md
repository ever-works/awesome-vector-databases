## Overview

Hamming distance is a metric for measuring similarity between binary vectors by counting the number of positions at which corresponding bits differ. It enables ultra-efficient vector search with minimal storage and computational requirements.

## How It Works

### Computation Method

1. **XOR Operation**: Compare each bit position using exclusive OR
2. **Count Differences**: XOR outputs 1 when bits don't match, 0 when they match
3. **Sum Results**: The count of 1's (Hamming weight/norm) is the distance

### Example

```
Vector A: 10110
Vector B: 10011
XOR:      00101
Hamming Distance: 2
```

## Storage Efficiency

### Binary Quantization

- Full precision: 1024 dimensions × 4 bytes = 4,096 bytes
- Binary: 1024 dimensions ÷ 8 bits = 128 bytes
- **32x storage reduction**

## Recent Applications (2026)

### Local-First RAG Systems

February 2026 implementations show:
- SQLite-based vector search using binary embeddings
- Hundreds of thousands of documents on commodity hardware
- No external vector database required
- Fully local semantic search

### Hybrid Search in SQLite

Multiple implementations published in early 2026 enable:
- Semantic search without external dependencies
- Combining with full-text search
- Running entirely on edge devices
- Privacy-preserving local AI

## Technical Implementation

### Platforms Supporting Hamming Distance

- SQLite (custom functions)
- Azure AI Search (binary vector fields)
- Oracle Database 26 (native support)
- Custom implementations in Python, JavaScript, Rust

### Performance Characteristics

- **Speed**: Extremely fast bitwise operations
- **Memory**: Minimal memory footprint
- **Accuracy**: Trade-off vs full precision (typically 90-95% recall)
- **Scalability**: Billions of vectors possible on single machines

## Use Cases

### High-Volume Applications

- Near-duplicate detection (web pages, images)
- Content deduplication
- Image retrieval systems
- Scientific databases
- Mobile and edge AI applications

### Resource-Constrained Environments

- IoT devices
- Mobile applications
- Browser-based AI
- Offline-first applications
- Privacy-sensitive deployments

## Advantages

- Minimal storage requirements
- Fast computation (bitwise operations)
- No specialized hardware needed
- Works on CPUs efficiently
- Easy to implement
- Supports exact and approximate search

## Limitations

- Loss of precision vs full vectors
- Not suitable for all use cases
- Requires good binary quantization strategy
- May need threshold tuning

## Integration Examples

Available in:
- MATLAB
- Python (NumPy, SciPy)
- JavaScript
- SQL databases
- Most programming languages

## Best Practices

- Use for first-stage retrieval, refine with full precision
- Test quantization strategy on your specific data
- Combine with filtering for better precision
- Consider hybrid approaches
- Benchmark against your use case