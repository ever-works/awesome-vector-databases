## Overview

BatANN is a distributed, disk-based vector search system designed for high-throughput approximate nearest neighbor (ANN) queries at scale. It addresses the challenge of performing efficient vector similarity search when vectors cannot fit entirely in memory, making it highly relevant for large-scale vector database systems.

## Key Features

- Distributed architecture for high-throughput ANN queries
- Disk-based storage design for vectors that exceed memory capacity
- Baton-based passing mechanism for efficient query routing
- Scalable to large-scale vector databases
- Optimized for approximate nearest neighbor search workloads

## Relevance

This system provides architectural patterns and methods applicable to the internal design of vector databases that need to handle more vectors than can fit in RAM, offering a cost-effective alternative to memory-only ANN search systems.