## Overview

embedded-vector-db is a self-contained Node.js library for efficient vector similarity search combined with BM25 full-text search and hybrid capabilities. Built on hnswlib-node for kNN search. Currently in beta with stable APIs expected in version 1.0.

## Features

- Hybrid Search: Combines semantic vector search with BM25 keyword search using weighted fusion or RRF
- Vector Search: kNN similarity using HNSW
- BM25 Full-Text Search: Industry-standard text ranking with tunable k1/b parameters
- Multi-namespace: Data isolation across collections
- CRUD Operations: insert, update, delete, batchInsert
- Metadata Filtering: Filter results by metadata fields
- Concurrency Safe: Thread-safe with mutex/semaphore
- Persistence: save/load indexes to disk
- Configuration: setFullTextIndexedFields, setBM25Params
- Reranking: Optional MMR diversity reranking

## Search Methods

- `search(namespace, queryVector, k)`: Pure vector search
- `fullTextSearch(namespace, queryText, k)`: BM25 keyword search
- `hybridSearch(namespace, queryVector, queryText, options)`: Weighted hybrid (vectorWeight/textWeight)
- `hybridSearchRRF(namespace, queryVector, queryText, k)`: RRF fusion (no tuning needed)

## Performance

For 10K documents (384-dim):
- Insert: 0.5-1ms
- Vector Search: 1-2ms
- BM25 Search: 1-3ms
- Hybrid RRF: 2-5ms

Memory: ~16MB for 10K docs.

## Pricing

Free and open-source under the MIT license.