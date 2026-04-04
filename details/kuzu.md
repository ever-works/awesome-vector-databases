## Overview

Kuzu is an embedded graph database built for query speed and scalability. It is optimized for handling complex analytical workloads on very large databases and provides retrieval features including full text search and vector indices.

## Features

- Flexible Property Graph Data Model with Cypher query language
- Embeddable, serverless integration into applications
- Native full text search and vector index
- Columnar disk-based storage
- Columnar sparse row-based (CSR) adjacency list/join indices
- Vectorized and factorized query processor
- Novel and very fast join algorithms
- Multi-core query parallelism
- Serializable ACID transactions
- Wasm (WebAssembly) bindings for fast, secure execution in the browser

## Extensions

Kuzu has an extension framework for dynamically loading functionality at runtime. Since v0.11.3, four commonly used extensions are pre-installed: algo, fts, json, and vector. For earlier versions or additional extensions, a local extension server must be set up using the provided Docker image (ghcr.io/kuzudb/extension-repo).

## Pricing

Free and open-source under the MIT License.