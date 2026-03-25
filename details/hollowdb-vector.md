## Overview

HollowDB Vector is a decentralized vector database for building vector search applications, developed by FirstBatch Labs. It implements Hierarchical Navigable Small Worlds (HNSW) index over HollowDB, combining decentralized storage with vector search capabilities.

## Core Technology

Built on HollowDB, a decentralized privacy-preserving key-value database on Arweave network, powered by Warp Contracts. The system provides a database for applications with production-level stability and feasibility for projects of any scale, while also being privacy-preserving.

## Key Features

- **Decentralized Architecture**: Runs on Arweave's permaweb for permanent, censorship-resistant storage
- **Privacy-Preserving Operations**: Data update and remove operations gated with zero-knowledge proofs
- **HNSW Indexing**: Implements state-of-the-art HNSW algorithm for efficient vector similarity search
- **Performance**: Write interaction ~1.5s on average, read interaction ~300ms on average with gRPC (bundled data)
- **Zero-Knowledge Proofs**: Users can only update key-value pairs by providing a zero-knowledge proof

## Use Cases

- Web3 AI applications requiring decentralized vector search
- Privacy-sensitive applications needing permanent, verifiable storage
- Decentralized knowledge bases and semantic search engines
- AI applications that need censorship-resistant vector databases

## Licensing

HollowDB Vector is licensed under Apache 2.0, making it free and open-source for commercial and non-commercial use.

## Pricing

Open-source and free to use. Storage costs are based on Arweave network fees for permanent data storage.