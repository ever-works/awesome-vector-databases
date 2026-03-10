## Overview

HNSW-IF (Hierarchical Navigable Small World - Inverted File) is Vespa's cost-efficient hybrid method for approximate nearest neighbor search, combining in-memory HNSW for centroids with disk-backed inverted file storage.

## Architecture

### Indexing Process
- Vectors that are not cluster centroids search for k closest centroids in HNSW graph
- Index closest centroid IDs using inverted indexes
- Inverted index dictionary maps centroid IDs to posting lists of non-centroid vector IDs

### Query Process
1. Search centroid vectors using HNSW for k closest centroids
2. Search inverted index using logical disjunction (OR) of retrieved centroid IDs
3. Access disk-backed vector data via memory-mapped forward index

## Cost Efficiency

- Traditional HNSW for 1B vectors (768 dims, float) requires ~4 TiB memory
- HNSW-IF keeps only centroids in memory
- Bulk of vector data stored on disk
- Dramatic cost reduction for billion-scale deployments

## Performance

- Searching 200M centroid vectors with HNSW: 2-3 ms single-threaded
- Maintains high accuracy with reduced memory footprint
- Scalable to billions of vectors

## Technical Details

- Vespa paged tensor attributes for disk-backed storage
- Memory-mapped forward index
- Posting lists don't contain vector data
- Efficient centroid-based retrieval

## Use Cases

- Billion-scale vector search on budget
- Cost-sensitive large-scale deployments
- Filtered vector search
- Hybrid keyword + semantic search

## Recognition

Noted in 2025 academic papers on vector database architectures as a leading approach for cost-efficient large-scale vector search.