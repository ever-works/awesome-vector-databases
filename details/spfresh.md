## Overview

SPFresh is a system that supports in-place vector updates, with LIRE (Lightweight Incremental REbalancing) at its core - a protocol to split vector partitions and reassign vectors in nearby partitions to adapt to data distribution shift.

## Key Performance Characteristics

- Provides superior query latency and accuracy to solutions based on global rebuild
- Uses only 1% of DRAM compared to state-of-the-art
- Requires less than 10% cores at peak for billion-scale vector index with 1% daily update rate
- Maintains 2.41x lower P99.9 latency than baselines
- Keeps high accuracy in dynamic scenarios
- Achieves 5.30x lower memory usage than baselines

## Technical Approach - LIRE Protocol

LIRE achieves low-overhead vector updates by only reassigning vectors at the boundary between partitions, where in a high-quality vector index the amount of such vectors are deemed small.

## Problem Addressed

Existing systems maintain a secondary index to accumulate updates, which are merged by the main index through global rebuilding. This approach has:
- High fluctuations of search latency and accuracy
- Substantial resource requirements
- Extremely time-consuming rebuilds

SPFresh eliminates the need for global index rebuilds through incremental in-place updates.

## Research

Published in October 2024 by USTC, Microsoft Research Asia, and Harvard University.

## Applications

Designed for applications requiring efficient vector index updates:
- Information retrieval
- Question answering systems
- Recommendation systems