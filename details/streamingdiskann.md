## Overview

StreamingDiskANN is a new index type developed by Timescale, inspired by Microsoft's DiskANN algorithm. It's explicitly designed for dynamically changing datasets that update continuously.

## Key Features

- **Disk-Based Storage**: Stores ANN index on disk rather than memory, using SSDs to handle terabytes of vectors
- **Streaming Post-Filtering**: Uses get_next() function to continuously retrieve nearest vectors until filter conditions are met
- **No Cutoff**: Unlike traditional ef_search, uses streaming model to potentially traverse entire graph
- **Dynamic Updates**: Designed for datasets that change continuously

## Performance

On 50 million Cohere embeddings (768 dimensions), PostgreSQL with pgvectorscale achieves:
- 28x lower p95 latency vs Pinecone's storage optimized index
- 16x higher query throughput
- 99% recall accuracy

## Technical Advantages

**Cost Efficiency**: Using SSDs enables terabyte-scale storage without prohibitive RAM costs

**Accurate Filtering**: Streaming approach guarantees accurate results even with secondary filters applied

**PostgreSQL Integration**: Seamlessly integrated via pgvectorscale extension

## Use Cases

- Large-scale vector search (billions of vectors)
- Applications with strict memory constraints
- Filtered vector search scenarios
- Real-time data ingestion with vector search

## Implementation

Available through pgvectorscale PostgreSQL extension.

## Pricing

Free and open-source (PostgreSQL license).