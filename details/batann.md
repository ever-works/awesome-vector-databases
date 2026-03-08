## Overview

BatANN is a distributed disk-based approximate nearest neighbor (ANN) system that retains the logarithmic search efficiency of a single global graph while achieving near-linear throughput scaling in the number of servers.

## Performance Results

- Achieves 6.21-6.49x throughput of scatter-gather baseline on 100M-point datasets at 0.95 recall
- Achieves 2.5-5.10x throughput on 1B-point datasets at 0.95 recall
- Maintains mean latency below 6ms using 10 servers
- Results achieved on standard TCP

## Core Innovation

When accessing a neighborhood stored on another machine, BatANN sends the full state of the query to the other machine to continue executing there. This "passing the baton" approach improves locality and reduces network overhead.

## Key Features

- First open-source distributed disk-based vector search system to operate over a single global graph
- Retains logarithmic search efficiency of centralized systems
- Near-linear throughput scaling with added servers
- Operates over standard TCP networking

## Technical Details

BatANN distributes a single global graph across multiple servers while maintaining search quality. The system sends query state between servers dynamically to optimize for data locality.

## Publication

Published on arXiv in December 2025 (2512.09331), representing recent advances in distributed vector search systems.

## Applications

Ideal for large-scale deployments requiring:
- Billion-scale vector search
- High throughput requirements
- Distributed infrastructure
- Low latency guarantees