## Overview

PlanetScale Vectors is a native vector search and storage solution built directly into MySQL. The service moved to general availability in 2025, bringing production-ready vector capabilities to the MySQL ecosystem.

## Key Features

- **Native MySQL Integration**: Store vector data alongside relational data with full ACID transaction support
- **Advanced Indexing**: Based on Microsoft Research's SPANN (Space-Partitioned Approximate Nearest Neighbors) and SPFresh algorithms
- **High Performance**: 2x query performance improvement and 8x better memory efficiency since beta
- **Large-Scale Support**: Vector indexes perform well even when 6x larger than available memory
- **Multiple Distance Metrics**: Supports Euclidean (L2), inner product, and cosine distance
- **High Dimensionality**: Stores vectors up to 16,383 dimensions
- **Quantization Support**: Both fixed and product quantization available
- **Standard SQL**: CREATE VECTOR INDEX and SELECT statements work with standard MySQL syntax

## Technical Implementation

Vectors are first-class citizens in PlanetScale MySQL:

- Writes and queries work like any other RDBMS operation
- Full JOIN and WHERE clause support in SELECT statements
- Transaction support with commit/rollback capabilities
- ALTER or CREATE VECTOR INDEX for index management

## Use Cases

- Semantic search applications
- Recommendation engines
- RAG (Retrieval-Augmented Generation) systems
- Similarity matching alongside transactional data
- Hybrid SQL and vector workloads

## Pricing

PlanetScale operates on a usage-based pricing model with vector-specific costs for storage and queries. Details available on the PlanetScale pricing page.