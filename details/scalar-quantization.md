## Overview

Scalar quantization compresses float values into narrower data types. Current implementations support int8 (8 bits), reducing vector index size fourfold.

## How It Works

Scalar quantization maps each float32 dimension (4 bytes) to an int8 representation (1 byte), achieving 4x memory compression through learned range mapping.

## Performance Characteristics

- **Compression**: 4x memory reduction
- **Recall**: Maintains 98-99% recall in testing
- **Compatibility**: Works with all embedding models
- **Precision**: Higher accuracy than binary quantization

## Recent Developments (2025-2026)

### 8-bit Rotational Quantization (RQ)
Provides 4x compression while maintaining 98-99% recall in internal testing. Represents an evolution of traditional scalar quantization.

### Azure AI Search Implementation
Supports int8 scalar quantization, achieving fourfold reduction in vector index size with minimal accuracy loss.

### PostgreSQL pgvector
Supports both scalar and binary quantization for vector search and storage optimization.

## Rescoring

Rescoring is used to offset information loss:
- Uses oversampling to retrieve extra vectors
- Applies supplemental information to rescore initial results
- Balances speed with accuracy

## Use Cases

- Production vector databases requiring balance between speed and accuracy
- Applications with large vector datasets
- Systems where 4x compression is sufficient
- Embeddings not centered around zero (where binary quantization performs poorly)

## Comparison with Other Methods

**vs. Binary Quantization**:
- Scalar: 4x compression, higher accuracy
- Binary: 32x compression, lower accuracy

**vs. Product Quantization**:
- Scalar: Simpler, per-dimension quantization
- Product: More complex, subvector-based compression

## Best Practices

- Use for general-purpose vector search
- Combine with rescoring for accuracy-critical applications
- Monitor recall metrics when implementing
- Consider binary quantization only if embeddings are zero-centered