## Overview

VQLite is a lightweight and simple vector similarity search engine based on Google ScaNN. VQLite provides a simple RESTful API for building vector similarity search services.

## Motivation

The reason for creating this project is that there is currently no solution that meets lightweight deployment needs. Vector search engines available on the market are often too heavy, requiring Kubernetes clusters with multiple replicas for deployment.

## Key Features

### Document-Oriented Approach
VQLite processes data based on documents as dimensions, which differs from common vector similarity search engines like Milvus, Qdrant, and Vearch that manage data by vector dimensions.

### Performance
VQLite uses Google's ScaNN at the core of the system since it may currently be the fastest public vector similarity search method available.

### Simple Deployment
- RESTful API for easy integration
- Deployment options through both source compilation and Docker
- Designed for developers who need efficient vector search without operational overhead

## Use Cases

- Developers needing vector search capabilities without complex infrastructure
- Small to medium-scale deployments
- Applications requiring fast vector similarity search with minimal setup
- Services where ScaNN's performance characteristics are beneficial

## Pricing

Free and open-source.