## Overview

Turbopuffer is a serverless vector and full-text search database built from first principles on object storage, providing fast, cost-effective, and extremely scalable search capabilities.

## Performance

- **Cold Queries**: p90=444ms for 1 million vectors (reads from object storage directly)
- **Warm Queries**: p50=8ms for 1 million cached vectors
- **Sub-10ms p50 latency**: When data is cached
- **Scale**: Hosts 2.5T+ documents, handles 10M+ writes/s, serves 10k+ queries/s

## Key Features

- **Serverless Architecture**: No infrastructure to manage
- **Object Storage-First**: Built on S3 or GCS for cost efficiency
- **Hybrid Search**: Vector search and BM25 full-text search
- **Automatic Tuning**: 90-100% recall without manual optimization
- **Clustered Indexes**: Uses clustered indexes rather than graph-based approaches (HNSW)
- **SSD Caching**: Frequently accessed data cached for ultra-low latency

## Cost Efficiency

Turbopuffer provides 10x cost savings compared to traditional vector databases:
- Object storage (S3/GCS): ~$0.02 per GB
- SSD caching: ~$0.1 per GB for hot data
- Pay only for what you use, no infrastructure overhead

## Architecture

Unlike graph-based approaches that require many round trips, Turbopuffer uses clustered indexes optimized for object storage, reducing latency and costs.

## Notable Users

- **Notion AI**: Powers AI-driven search and recommendations
- **Linear**: Issue search functionality
- **Superhuman**: Email search capabilities
- **Telus**: Enterprise AI copilot
- **Cursor**: Repository indexing (95% cost reduction)

## Use Cases

- Large-scale semantic search
- RAG (Retrieval-Augmented Generation) systems
- Recommendation engines
- Enterprise search applications
- Code repository indexing
- Email and document search
- Customer support knowledge bases

## Pricing

Serverless pricing based on:
- Storage usage
- Query volume
- Data transfer

10x more cost-effective than traditional vector database solutions.