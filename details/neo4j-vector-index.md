## Overview

Neo4j Vector Index brings vector similarity search to the leading graph database, enabling powerful hybrid queries that combine graph relationships with semantic similarity. As of Neo4j 2026.01, the preferred way of querying is using the Cypher SEARCH clause.

## Features

- **HNSW Implementation**: Uses Hierarchical Navigable Small World algorithm
- **Graph + Vector**: Combine relationship traversal with similarity search
- **Multi-Label Support**: Vector indexes can span multiple node labels
- **Filtered Search**: Filter vector searches by properties and relationships
- **Cypher Integration**: Native vector operations in Cypher query language
- **Real-Time Updates**: Vector indexes update as embeddings change
- **Knowledge Graphs**: Perfect for graph-enhanced RAG applications

## Use Cases

- Knowledge graph-enhanced RAG
- Recommendation systems using graph context
- Entity resolution with semantic similarity
- Fraud detection combining patterns and similarity
- Scientific literature analysis
- Social network analysis with semantic search

## Performance

While Neo4j shows good performance with smaller datasets, specialized vector databases may outperform it at very large scale. The advantage is the unified graph + vector model.

## Integration

Works with LangChain and LlamaIndex. Embeddings from any model can be stored and searched. Popular with organizations already using Neo4j.

## Query Example

Use Cypher's SEARCH clause to find similar nodes based on vector embeddings while traversing graph relationships.

## Pricing

Available in Neo4j Community Edition (free) and Enterprise Edition. AuraDB cloud offering includes vector capabilities.