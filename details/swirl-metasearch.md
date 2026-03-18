## Overview

Swirl is an open-source enterprise-grade AI-powered federated search platform that searches across 100+ enterprise platforms simultaneously without requiring data migration, indexing, or duplication.

## Metasearch Architecture

### How Federation Works
Rather than gathering data into a central repository, Swirl leaves information in place and connects natively to sources wherever they reside:
- Structured databases
- Unstructured file shares
- Collaboration apps (Slack, Teams, etc.)
- Cloud services (S3, Google Drive, SharePoint)
- Websites and APIs
- Search engines

### Search Process
1. Asynchronously sends user queries to authorized APIs and configured endpoints
2. Waits for responses (time depends on slowest source)
3. Re-ranks results from all responding sources using LLM embeddings
4. Presents unified, AI-ranked results to users

## Key Features

### No Data Migration Required
- Connects to data where it lives
- No indexing or extraction needed
- No vector database setup required
- Preserves data security and compliance

### AI-Powered Re-ranking
- Uses Large Language Models for result ranking
- Embeddings from configured LLM improve relevance
- Unified results across disparate sources
- Context-aware result presentation

### Broad Connectivity
- Adapts and distributes queries to anything with a search API
- Supports search engines, databases, NoSQL engines
- Cloud/SaaS service integration
- Custom connector development supported

## Components

### Metasearch Engine
- Sends user search requests to multiple sources simultaneously
- Parallel query execution for speed
- Handles varied response formats
- Manages authentication per source

### Content Transformation
- Normalizes results from different sources
- Applies AI ranking algorithms
- Enhances result snippets
- Provides unified result format

## Enterprise Benefits

### Security
- Data stays in place, maintaining existing security controls
- Role-based access control to sources
- Audit trail of search activities
- Compliance with data residency requirements

### Quick Deployment
- Deploy in minutes, not months
- No lengthy migration projects
- Immediate ROI
- Minimal infrastructure changes

### Scalability
- Searches across 100+ platforms
- Handles enterprise-scale queries
- Distributed architecture
- Cloud-native design

## Use Cases

- **Enterprise Search**: Unified search across all company data sources
- **Knowledge Management**: Find information regardless of where it's stored
- **Customer Support**: Search across ticketing, documentation, and knowledge bases
- **Legal Discovery**: Search documents across multiple repositories
- **Research & Development**: Find information across research databases and documents

## Integration

### Supported Sources
- Microsoft 365 (SharePoint, OneDrive, Teams)
- Google Workspace (Drive, Docs)
- Slack, Confluence, Jira
- Databases (SQL, NoSQL)
- Cloud storage (S3, Azure Blob, GCS)
- Custom APIs and services

### Deployment Options
- Self-hosted on-premises
- Cloud deployment
- Hybrid configurations
- Docker containers

## Open Source

Available on GitHub: https://github.com/swirlai/swirl-search

Free and open-source with community support and enterprise options available.