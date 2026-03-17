## Overview

Voy is a WASM vector similarity search engine written in Rust with an exceptionally small footprint of only 75KB gzipped (69KB brotli). It enables semantic search in browsers, edge environments, and IoT devices without requiring server-side infrastructure.

## Key Features

- **Tiny Footprint**: Only 75KB gzipped, 69KB with brotli compression, reducing overhead for limited devices like mobile browsers and IoT
- **Fast**: Optimized for creating the best search experience with efficient k-d tree indexing
- **Tree Shakable**: Optimizes bundle size and enables asynchronous capabilities for modern Web APIs like Web Workers
- **Resumable**: Generate portable embeddings index anywhere, anytime
- **Worldwide**: Designed to deploy and run on CDN edge servers
- **Browser Support**: Runs in non-Node environments including all modern browsers

## Technical Implementation

- **Data Structure**: Uses k-d tree (k-dimensional tree) to organize and store embeddings
- **Distance Metric**: Internally uses Squared Euclidean distance to calculate nearest neighbors
- **WASM**: Compiled to WebAssembly from Rust for portability and performance

## Design Principles

Voy follows several core design principles:
1. Minimize size for limited devices (mobile browsers, IoT)
2. Optimize for fast search performance
3. Enable tree shaking for bundle optimization
4. Support modern Web APIs like Web Workers
5. Create portable, resumable indexes
6. Enable edge deployment on CDNs

## Integration

- **LangChain.js**: Voy can be used as a vector store with LangChain.js
- **npm Package**: Available as `voy-search` on npm
- **Installation**: Can be installed via npm, Yarn, or pnpm

## Simple Interface

Voy provides a straightforward API with just two main operations:
1. Index construction
2. Querying an index for nearest neighbors

## Development Status

Voy is under active development. The API is not yet stable, and there may be breaking changes before the 1.0 release.

## Use Cases

- Client-side semantic search in web applications
- Edge computing vector search
- Mobile browser search functionality
- IoT device similarity search
- Offline-first applications
- CDN-deployed search services

## Resources

- **GitHub**: https://github.com/tantaraio/voy
- **npm**: voy-search package
- **Language**: Rust (compiled to WASM)