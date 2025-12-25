## jvector

**Category:** SDKs & Libraries  
**Type:** Java library for vector search and approximate nearest neighbor (ANN) indexing

jvector is a high-performance, Java-based engine for approximate nearest neighbor search, combining ideas from HNSW and DiskANN/Vamana to provide scalable, graph-based vector indexing.

### Features

- **Graph-based ANN index**
  - Implements a graph index merging the DiskANN and HNSW design families.
  - Uses a hierarchical (multi-layer) graph structure similar to HNSW.
  - Employs the Vamana algorithm (from DiskANN) within each layer.

- **Hierarchical / multi-layer architecture**
  - Upper layers of the hierarchy are maintained in memory as per-node adjacency lists.
  - Enables fast navigation of the index with no disk I/O for upper-level traversals.
  - Bottom layer is stored on disk as per-node adjacency lists for large-scale datasets.

- **Two-pass search support**
  - Stores additional data inline in the on-disk layer to enable two-pass search strategies.
  - First pass is designed to be powered by lightweight, I/O-efficient access patterns.

- **High performance and scalability**
  - Non-blocking concurrency control for index construction.
  - Construction scales linearly with the number of CPU cores (parallel index build).
  - Designed for high-dimensional vector search where exact KNN is impractical.

- **Approximate nearest neighbor (ANN) capabilities**
  - Optimized for logarithmic-time approximate nearest neighbor search on large datasets.
  - Suitable for dynamic, general-purpose indexing where incremental construction and updates are needed.

### Typical Use Cases

- Large-scale vector search over high-dimensional embeddings.
- Applications requiring fast approximate nearest neighbor queries (e.g., semantic search, recommendation, similarity search).
- Systems needing incremental or continuously updated ANN indexes rather than static, pre-built indexes.

### Pricing

- Not specified in the provided content (open-source GitHub project; see repository for license and usage terms).