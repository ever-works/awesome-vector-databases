## Overview

Statistical Binary Quantization (SBQ) is an advanced compression method developed by Timescale researchers that improves upon standard Binary Quantization for vector search applications.

## Key Innovation

SBQ provides superior compression compared to traditional binary quantization while maintaining accuracy, particularly important for filtered vector search operations.

## Compression Benefits

- **32x Compression**: Reduces vector storage by factor of 32
- **Maintained Accuracy**: Preserves search quality despite aggressive compression
- **Cost Efficiency**: Dramatically reduces storage and memory costs

## Technical Approach

Builds on Binary Quantization (BQ) which reduces each float32 value to a single bit, but adds statistical methods to improve accuracy. Works particularly well with DiskANN-based indexes for filtered searches.

## Use Cases

- Large-scale vector databases with memory constraints
- Cost-sensitive applications
- Filtered vector search scenarios
- PostgreSQL-based vector applications

## Integration

Available as part of the pgvectorscale PostgreSQL extension, working alongside StreamingDiskANN indexing.

## Performance Characteristics

- Enables billion-scale vector search on commodity hardware
- Maintains high recall rates (>99%)
- Significantly faster than uncompressed approaches for filtered search

## Comparison to Other Methods

- **vs Standard BQ**: Better accuracy through statistical optimization
- **vs Product Quantization**: Simpler implementation, good for binary scenarios
- **vs Scalar Quantization**: Higher compression ratio

## Pricing

Free and open-source as part of pgvectorscale.