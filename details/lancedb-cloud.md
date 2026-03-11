## Overview

LanceDB Cloud is a fully managed, serverless vector search service that enables developers to build, deploy, and scale AI-powered applications without infrastructure management overhead.

## Key Features

- **Serverless Architecture**: Zero infrastructure to manage
- **Automatic Operations**: Automatic indexing, compaction, and data cleanup
- **Intuitive UI**: Web interface to explore and manage data
- **Multi-Language SDKs**: Python, TypeScript, and Rust support
- **Enterprise-Grade**: Reliability, security, and performance at scale
- **Seamless Migration**: Same SDK as LanceDB OSS with connection string change

## Advantages Over Self-Hosting

### Operational Benefits

- No server maintenance or scaling concerns
- Automatic performance optimization
- Built-in monitoring and alerting
- Managed backups and disaster recovery
- Security updates handled automatically

### Developer Experience

- Same API as open-source LanceDB
- Simple migration path from local to cloud
- Consistent development experience
- No vendor lock-in (can move back to OSS)

## Migration Path

Transition from LanceDB OSS to Cloud is straightforward:

1. Change connection string to point to remote database
2. No code changes required beyond connection
3. Same SDK, same API, same functionality
4. Can switch back to local development anytime

## Technical Capabilities

Inherits all features from LanceDB OSS:
- **Multimodal Support**: Text, images, video, documents
- **Fast Search**: Sub-millisecond query latency
- **Hybrid Search**: Vector + full-text search
- **Scalability**: Handles billions of vectors
- **Production-Ready**: Built on Apache Lance format

## AWS Integration

LanceDB Cloud can be deployed on AWS with:
- S3-based storage for cost efficiency
- Elastic scaling for 1B+ vectors
- Integration with AWS services
- High availability across regions

## Pricing

### Starter Plan

- Starts at **$16.03/month**
- **$100 free credits** (one-time) for first month
- Pricing components:
  - Write operations
  - Query operations
  - Storage usage

### Usage-Based Billing

- Pay only for what you use
- No upfront costs
- Transparent pricing model
- Scale up or down automatically

## Use Cases

- RAG (Retrieval-Augmented Generation) applications
- Semantic search at scale
- Recommendation engines
- Similarity matching
- Image and video search
- Document retrieval
- AI agent memory systems

## OSS vs Cloud Decision

### Choose LanceDB OSS when:

- Building and prototyping locally
- Full control over infrastructure required
- Cost optimization through self-hosting
- Integration with existing backend applications

### Choose LanceDB Cloud when:

- Production deployments at scale
- Want to avoid infrastructure management
- Need automatic scaling and operations
- Prefer managed services
- Require enterprise support

## Support

- Technical documentation
- Community support (Discord, GitHub)
- Enterprise support plans available
- Migration assistance

## Free Tier

LanceDB OSS remains forever free for:
- Local development
- Self-hosted deployments
- Building and integration