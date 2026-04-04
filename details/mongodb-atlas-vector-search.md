## Overview

MongoDB Atlas Vector Search is a native vector search capability integrated into MongoDB Atlas. It leverages Lucene-based k-nearest neighbor (kNN) search, enabling hybrid search that combines vector similarity with MongoDB's native document query capabilities and full-text search.

## Key Features

- **Lucene-Based kNN Search**: Approximate nearest neighbor search using HNSW graphs with Lucene indexing
- **Hybrid Search**: Combines vector queries with metadata filters, aggregation pipelines, geo-spatial search, and lexical text search
- **Document Database Integration**: Operates within MongoDB's native document model—no separate vector database needed
- **Full-Text Search**: Built-in lexical and text-based search alongside vector search
- **$vectorSearch Stage**: Dedicated aggregation pipeline stage for vector queries with the MongoDB Query API
- **Quantization Support**: Scalar and binary quantization for reduced memory footprint
- **Scalability**: Scales independently from primary MongoDB workloads
- **Global Availability**: Available in 125+ regions via MongoDB Atlas
- **Ecosystem Integrations**: Works with LangChain, LlamaIndex, OpenAI, Haystack, and other AI frameworks

## Use Cases

- Retrieval-augmented generation (RAG)
- Semantic and similarity search
- Recommendation engines
- Conversational AI and chatbots
- Anomaly detection

## Pricing

Part of the MongoDB Atlas platform. Pricing is based on underlying cluster resources including compute, storage, and search nodes. See [mongodb.com/pricing](https://www.mongodb.com/pricing) for details.