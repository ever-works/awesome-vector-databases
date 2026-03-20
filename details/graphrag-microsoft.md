## Overview

GraphRAG is Microsoft's knowledge graph-enhanced approach to Retrieval Augmented Generation, addressing limitations of traditional vector-only RAG through structured knowledge representation.

## How It Works

1. **Document Processing**: Extract entities and relationships
2. **Graph Construction**: Build knowledge graph from documents
3. **Community Detection**: Identify topical clusters
4. **Hierarchical Summarization**: Create multi-level summaries
5. **Graph-Enhanced Retrieval**: Query using graph structure

## Advantages Over Traditional RAG

**Better Context**:
- Understand document structure
- Capture relationships
- Multi-hop reasoning

**Complex Queries**:
- Answer questions requiring synthesis
- Handle multi-document reasoning
- Support exploratory queries

**Improved Coverage**:
- Community summaries for broad queries
- Fine-grained retrieval for specific questions

## Use Cases

- Complex document analysis
- Enterprise knowledge bases
- Research literature review
- Multi-document summarization
- Investigative queries

## Components

- Entity extraction (NER)
- Relationship extraction
- Graph database (Neo4j compatible)
- Vector embeddings for semantic search
- LLM for synthesis

## Availability

Open-source: microsoft/graphrag on GitHub