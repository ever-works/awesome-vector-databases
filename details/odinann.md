## Overview

OdinANN is a billion-scale graph-based ANNS (Approximate Nearest Neighbor Search) index with direct inserts, designed to address performance challenges in disk-based vector search systems.

## Key Performance Features

### Insertion Stability
Provides direct insert for consistently stable performance in billion-scale graph-based vector search, a significant improvement over previous systems like DiskANN that use batch-merge approaches.

### Search Performance
- Extremely low search latency: <1ms in billion-scale vectors (top-10, 90% recall)
- Only 1.14x-2.02x latency of in-memory graph-based index
- More than 10x less memory usage compared to in-memory solutions
- Low and stable search latency during insertions

## Technical Innovations

### Direct Insertion
Utilizes direct insertion into the on-disk index, avoiding the costly batch-merge process that hampers other systems.

### Two Main Techniques
1. **GC-free design** - Reduces disk write overhead
2. **Update combining** - Strategic page provisioning for efficient updates

## Publication and Availability

Presented at the 24th USENIX Conference on File and Storage Technologies (FAST 26), Santa Clara, CA, 2026. Implementation available as an artifact repository for the FAST'26 accepted paper.

## Use Cases

Ideal for applications requiring:
- Billion-scale vector search
- Low-latency requirements
- Memory-constrained environments
- Frequent index updates