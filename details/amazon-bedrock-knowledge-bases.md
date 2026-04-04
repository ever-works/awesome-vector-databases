## Overview

Amazon Bedrock Knowledge Bases is a fully managed capability within Amazon Bedrock that simplifies building retrieval-augmented generation (RAG) applications. It automates the end-to-end workflow from data ingestion to embedding storage and retrieval, allowing developers to ground generative AI model responses with their own enterprise data.

## Data Sources

### Unstructured Data
- Amazon Simple Storage Service (Amazon S3)
- Confluence
- Salesforce
- SharePoint
- Web Crawler (preview)
- Programmatic document ingestion for streaming data or unsupported sources

### Structured Data
- Data warehouses
- Data lakes
- Transactional data stores

## How It Works

1. **Data Ingestion**: Automatically fetches content from configured data sources.
2. **Text Processing**: Converts ingested content into blocks of text.
3. **Embedding Generation**: Transforms text blocks into vector embeddings.
4. **Vector Storage**: Stores embeddings in a chosen vector database.

## Supported Vector Stores

- Amazon Aurora
- Amazon OpenSearch Serverless
- Amazon Neptune Analytics
- MongoDB
- Pinecone
- Redis Enterprise Cloud

## Hybrid Search Option

- Amazon Kendra hybrid search index for managed retrieval.

## Structured Data Querying

- Uses Natural Language to SQL to convert user queries into SQL commands.
- Executes commands against structured data stores to retrieve results.
- No need to move data from its original source.
- Particularly useful for transactional details stored in data warehouses and data lakes.

## Pricing

Pay-as-you-go pricing based on usage. Refer to the [Amazon Bedrock pricing page](https://aws.amazon.com/bedrock/pricing/) for details.