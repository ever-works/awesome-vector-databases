## Overview

The vss extension is an experimental extension for DuckDB that adds indexing support to accelerate vector similarity search queries using DuckDB's new fixed-size ARRAY type.

## Key Features

### HNSW Index Support
The vss extension introduces support for HNSW (Hierarchical Navigable Small Worlds) indexes to accelerate vector similarity search.

### Distance Metrics
By default the HNSW index will be created using the euclidean distance l2sq (L2-norm squared) metric, matching DuckDB's array_distance function, but other distance metrics can be used by specifying the metric option during index creation. Supported metrics include:
- l2sq (L2-norm squared)
- cosine similarity
- inner_product

## Installation

The extension can be installed by running:
```sql
INSTALL vss;
LOAD vss;
```

## Creating an Index

Here's an example of creating an HNSW index:
```sql
CREATE INDEX my_hnsw_index 
ON my_vector_table 
USING HNSW (vec);
```

Or with a specific metric:
```sql
CREATE INDEX my_hnsw_cosine_index 
ON my_vector_table 
USING HNSW (vec) 
WITH (metric = 'cosine');
```

## Technical Details

### Implementation
The extension is based on the usearch library and represents DuckDB's first custom index type provided through an extension.

### Limitations
The index itself is not buffer managed and must be able to fit into RAM memory. However, the index will be persisted into the database if you run DuckDB with a disk-backed database file.

## Recent Updates

The vector search extension has received new performance optimizations with new features and improvements since the initial release.

## Use Cases

- AI applications requiring vector search in analytical queries
- Embeddings storage and retrieval
- Semantic search use cases
- Combining vector search with DuckDB's analytical capabilities

## Pricing

Free and open-source as part of DuckDB.