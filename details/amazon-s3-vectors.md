## Overview

Amazon S3 Vectors provides native vector storage and querying in S3 vector buckets and indexes. Fully serverless with no infrastructure management.

## Key Capabilities

- Store up to 2 billion vectors per index (40x increase from preview)
- Up to 20 trillion vectors per vector bucket
- Query latencies: <1s infrequent, ~100ms frequent queries
- Retrieve up to 100 results per query
- Write throughput: 1,000 PUT/s for single-vector updates
- Supports float32 data type, cosine and Euclidean distance metrics
- Up to 50 metadata keys per vector (10 non-filterable)
- Filterable metadata for hybrid similarity + metadata filtering

## Integrations

- Amazon Bedrock Knowledge Bases (vector storage engine for RAG)
- Amazon OpenSearch Service (vector storage layer)
- AWS CLI (s3vectors commands)
- AWS Console management
- AWS CloudFormation, AWS PrivateLink, resource tagging

## Management

- Create vector buckets and indexes via CLI or Console
- Bucket/index-level encryption (SSE-S3 or KMS)
- Tags for access control and cost allocation
- Properties and permissions management in Console

## Pricing

Pay-per-use model:
- **PUT**: Per logical GB uploaded (vector + metadata + key)
- **Storage**: Per logical GB across indexes
- **Query**: Per API call + $/TB scanned (tiered: lower rates >100k vectors)

Details: [Amazon S3 Pricing](https://aws.amazon.com/s3/pricing/)

## Availability

14 AWS Regions: US East (Ohio, N. Virginia), US West (Oregon), Europe (Frankfurt, Ireland, London, Paris, Stockholm), Asia Pacific (Mumbai, Seoul, Singapore, Sydney, Tokyo), Canada (Central)

## Use Cases

- Retrieval Augmented Generation (RAG)
- Semantic search
- Conversational AI
- Multi-agent workflows
- AI agents and inference