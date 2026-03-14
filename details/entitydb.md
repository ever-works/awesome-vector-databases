## Overview

EntityDB is a powerful, lightweight in-browser database designed for storing and querying vectors. It integrates seamlessly with IndexedDB for persistent storage and Transformers.js to generate embeddings from text, allowing you to build fast and efficient search systems with state-of-the-art models.

## Key Features

- **Browser-Native**: Runs entirely in the browser using IndexedDB for local storage
- **Transformers.js Integration**: Seamlessly generate text embeddings with Hugging Face models via Transformers.js
- **Cosine Similarity Search**: Efficient querying based on cosine similarity between vectors
- **Flexible**: Supports both automatic embedding generation and manual insertion of pre-computed embeddings
- **No Server Required**: No need for a server-side component or complex setup
- **WebAssembly SIMD**: Leverages WebAssembly SIMD for performance optimization

## Use Cases

- Build search engines
- Recommendation systems
- AI memory applications
- Any app requiring vector similarity search
- Fully decentralized IPFS intelligent entities

## Installation

Install via npm as `@babycommando/entity-db`.

## Resources

- GitHub: https://github.com/babycommando/entity-db
- Landing Page: https://entity-db-landing.vercel.app/