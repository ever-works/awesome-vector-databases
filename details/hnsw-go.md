# HNSW (Go)

**Category:** SDKs & Libraries  
**Technology:** Go, Approximate Nearest Neighbor (ANN), Vector Search  
**Source:** https://github.com/coder/hnsw

## Overview
HNSW (Go) is a Go implementation of Hierarchical Navigable Small World (HNSW) graphs for fast approximate nearest neighbor (ANN) search over high-dimensional vectors. It can serve as an in-memory alternative to a vector database, suitable for embedding vector similarity search directly into Go applications and custom vector databases.

## Features

### Core Functionality
- **In-memory HNSW graph implementation** in pure Go.
- **Approximate nearest neighbor search** for high-dimensional vector data.
- Designed as an **in-memory alternative to vector databases** (e.g., Pinecone, Weaviate) with essential operations.

### Data Model & Operations
- **Insert**
  - Operation: Insert a vector into the graph.
  - Complexity: ~O(log n).
- **Delete**
  - Operation: Delete a vector from the graph.
  - Complexity: ~O(M² · log n), where M is the maximum number of neighbors per node.
- **Search**
  - Operation: Search for nearest neighbors of a query vector.
  - Complexity: ~O(log n).
- **Lookup**
  - Operation: Retrieve a vector by ID.
  - Complexity: O(1).
- **Configurable construction parameters** (e.g., M, mL/`Graph.Ml`) to trade off speed, recall, and memory usage, following the original HNSW paper.

### Go API & Usage
- Simple **Go module import**:
  ```bash
  go get github.com/coder/hnsw@main
  ```
- **Graph creation** via `hnsw.NewGraph[IDType]()`, where the ID is generic (e.g., `int`).
- **Node creation** with `hnsw.MakeNode(id, []float32{...})`.
- **Vector addition** using `Graph.Add(...)`.
- **Nearest neighbor search** using `Graph.Search(queryVector, k)`.

### Persistence & Serialization
- **In-memory graph operations** with optional persistent storage support.
- **Import/Export via streams**:
  - `Graph.Export(io.Writer)` — write graph to an `io.Writer`.
  - `Graph.Import(io.Reader)` — load graph from an `io.Reader`.
- **File-backed SavedGraph** abstraction:
  - `LoadSavedGraph[T](path)` to load or initialize a graph backed by a single file.
  - `SavedGraph.Save()` to persist the current graph state to disk.
- Uses a **fast binary encoding** for the graph to achieve near disk-speed save/load performance (benchmarks provided for import/export on 100 vectors × 256 dimensions).

### Performance & Tuning
- Designed for **fast querying** with approximate nearest neighbor results.
- Performance characteristics:
  - At high dimensionality (e.g., 1536 dimensions), a large portion of query time is spent in the distance function.
- Suggested tuning guidelines:
  - To reduce **latency**:
    - Reduce vector dimensionality.
    - Increase `M` (maximum neighbors per node) for better search behavior at the cost of memory.
  - To reduce **memory usage**:
    - Decrease `Graph.M` (M — maximum neighbors per node).
    - Decrease `Graph.Ml` (mL — level generation parameter).

## Pricing
Not applicable. HNSW (Go) is an open-source Go library; no pricing information is provided in the source content.