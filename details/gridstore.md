## Overview

GridStore is Qdrant's custom-built storage engine that was introduced in Qdrant Version 1.13 for payload and sparse vector storages. Qdrant is built entirely in Rust with SIMD and a custom storage engine (Gridstore) — no wrappers, no bolt-ons.

## Why GridStore Was Built

When Qdrant started, they used RocksDB as their embedded key-value store, but ran into issues such as random latency spikes due to its architecture. Gridstore is their custom solution to these and other challenges they faced when building with RocksDB.

## Architecture

GridStore was developed in Rust and has a data layer to store values in fixed-size blocks for fast lookups, a mask layer to track used and unused blocks without needing compaction, plus a gaps layer to manage space allocation.

## Migration from RocksDB

In Qdrant v1.17.x, RocksDB support was completely removed in favor of gridstore, meaning that direct upgrade from v1.15.x to v1.17.x wouldn't be possible. The system is actively migrating away from RocksDB towards Gridstore for appendable segments and Mmap for non-appendable segments.

## Performance Improvements

To measure the impact of the new storage engine, Qdrant used Bustle, a key-value storage benchmarking framework, to compare Gridstore against RocksDB across three workloads. Average latency for all kinds of workloads is lower across the board, particularly for inserts, showing a clear boost in performance.

## Pricing

Open-source as part of Qdrant.