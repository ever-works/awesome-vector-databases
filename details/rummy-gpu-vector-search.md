## Overview

RUMMY is the first GPU-accelerated vector query processing system that achieves high performance and supports large vector datasets beyond GPU memory. Developed by researchers from Peking University, the system was presented at USENIX NSDI '24.

## Key Features

- **Reordered Pipelining**: Exploits characteristics of vector query processing to efficiently pipeline data transmission from host memory to GPU memory and query processing in GPU
- **Cluster-Based Retrofitting**: Eliminates redundant data transmission across queries in a batch
- **Dynamic Kernel Padding**: Maximizes spatial and temporal GPU utilization for GPU computation with cluster balancing
- **Query-Aware Optimization**: Reorders and groups queries to optimally overlap transmission and computation

## Performance

- Outperforms IVF-GPU with CUDA unified memory by up to 135×
- Achieves up to 23.1× better performance compared to CPU-based solutions (with 64 vCPUs)
- Up to 37.7× more cost-effective than CPU implementations

## Use Cases

- Billion-scale vector similarity search
- Maximum inner product search (MIPS)
- Large-scale semantic search applications
- GPU-accelerated RAG systems

## Technical Architecture

RUMMY addresses the challenge of processing vector queries on datasets that exceed GPU memory capacity. The core innovation is a novel reordered pipelining technique that leverages three key ideas to achieve optimal performance with limited GPU memory.

## Availability

RUMMY is open-source and available on GitHub at pkusys/Rummy.