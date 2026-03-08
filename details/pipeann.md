## Overview

PipeANN is a low-latency, billion-scale, and updatable graph-based vector store (vector database) on SSD developed by Tsinghua University's Storage Research Group.

## Key Features

### Search Performance
- Extremely low search latency of <1ms in billion-scale vectors (top-10, 90% recall)
- Only 1.14x-2.02x latency of in-memory graph-based index
- More than 10x less memory usage (e.g., 40GB for billion-scale datasets)
- High search throughput of 20K QPS in billion-scale vectors
- Higher throughput than DiskANN with beam_width=8 (latency-optimal) and SPANN

### Update Support
- Efficient vector updates: insert and delete operations
- Minimal interference with concurrent search (fluctuates only 1.07x)
- Reduced memory usage (less than 90GB for billion-scale datasets)

## Technical Approach

PipeANN is an on-disk graph-based approximate nearest neighbor search (ANNS) system that bridges the latency gap with in-memory systems by aligning the best-first search algorithm with SSD characteristics, avoiding strict compute-I/O order across search steps.

## Publications

- "Achieving Low-Latency Graph-Based Vector Search via Aligning Best-First Search Algorithm with SSD" - OSDI '25 (2025)
- "OdinANN: Direct Insert for Consistently Stable Performance in Billion-Scale Graph-Based Vector Search" - FAST '26 (2026)

## Availability

Open-source code available on GitHub from Tsinghua University and UIUC.