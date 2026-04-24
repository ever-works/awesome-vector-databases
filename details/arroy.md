## Overview
Arroy provides efficient on-device vector search with low-latency ANN using LMDB backend.

## Features
- Low-latency ANN search with random projection trees
- LMDB for concurrent read/write access
- Configurable n_trees and search_k for latency/accuracy trade-off
- Multi-threaded queries

## Use Cases
- IoT real-time similarity search
- On-device AI embeddings management
- CV inference on edge hardware

## Comparisons
- On-device low-latency vs cloud Qdrant servers
- Lower memory than Annoy, persistent unlike in-memory only libs

## Pricing
Free open-source (MIT).