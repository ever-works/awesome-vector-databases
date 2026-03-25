## Overview

Snowflake Cortex Search is a managed service that provides a hybrid search approach to retrieving and ranking documents. It utilizes vector search for semantic similarity, keyword search for lexical matching, and semantic reranking for optimal relevance.

## Recent Updates (March 2026)

- Support for pre-computed vector embeddings from third-party models
- Dynamic filters for applying filter conditions on each search call
- Dynamic columns to specify which metadata columns to retrieve per call
- Dynamic result count up to 500 results per call
- Enhanced hybrid retrieval capabilities

## How It Works

Cortex Search takes a hybrid approach:

- **Vector Search**: Retrieves semantically similar documents using embeddings
- **Keyword Search**: Retrieves lexically similar documents using traditional search
- **Semantic Reranking**: Reranks the most relevant documents in the result set

## Key Features

- Serverless architecture integrated with Snowflake Data Cloud
- Support for both Snowflake-provided embeddings and custom pre-computed vectors
- Dynamic search behavior control via API parameters
- Attribute-based filtering during search
- Metadata column selection per query
- Enterprise-grade security and governance

## Cost Structure

- Embedding tokens charged during index creation
- Ongoing serving costs per GB of index maintained
- Different pricing model than AISQL functions
- Usage-based billing integrated with Snowflake credits

## Use Cases

- Enterprise knowledge bases and document retrieval
- Semantic search over structured and unstructured data
- RAG applications with Snowflake data
- Compliance-sensitive AI applications requiring data governance

## Integration

Fully integrated with Snowflake ecosystem including Snowpark, Streamlit, and Snowflake's security features.