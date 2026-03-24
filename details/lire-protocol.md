## Overview

LIRE (Lightweight Incremental Rebalancing Protocol) is the core algorithm in SPFresh that enables in-place vector updates for billion-scale vector indexes.

## How It Works

LIRE achieves low-overhead vector updates by only reassigning vectors at the boundary between partitions, where in a high-quality vector index the amount of such vectors are deemed small. The protocol splits vector partitions and reassigns vectors in nearby partitions to adapt to data distribution shifts.

## Performance Benefits

With LIRE, SPFresh provides superior query latency and accuracy to solutions based on global rebuild, with only 1% of DRAM and less than 10% cores needed at the peak compared to the state-of-the-art, in a billion scale vector index with 1% of daily vector update rate.

## Problem Solved

Traditional systems maintain a secondary index to accumulate updates, which are merged by the main index by globally rebuilding the entire index periodically. This approach has high fluctuations of search latency and accuracy, requires substantial resources, and is extremely time-consuming for rebuilds.

## Real-World Adoption

The LIRE protocol has been adopted in production systems like Turbopuffer for billion-scale vector search with incremental updates.

## Pricing

Open-source research algorithm.