## Overview

Hybrid search combines the strengths of traditional keyword-based search (typically BM25) with modern semantic vector search. This approach captures both exact keyword matches and semantic similarities, providing more robust retrieval than either method alone.

## How It Works

### Dual Retrieval

1. **BM25 (Keyword Search)**: Finds documents with exact or partial keyword matches
2. **Vector Search**: Finds semantically similar documents using embeddings
3. **Fusion**: Combines results using algorithms like RRF (Reciprocal Rank Fusion)

## Key Advantages

- **Best of Both Worlds**: Captures exact matches AND semantic meaning
- **Handles Terminology**: BM25 catches specific terms, jargon, IDs
- **Semantic Understanding**: Vector search finds conceptually similar content
- **Improved Recall**: Less likely to miss relevant documents
- **Robustness**: Works well across diverse query types

## Fusion Methods

### Reciprocal Rank Fusion (RRF)
Most common approach:
- Score = 1/(rank + k) for each result
- Combines scores from both methods
- Parameter k typically set to 60

### Linear Combination
- Weighted sum of BM25 and vector scores
- Requires score normalization
- Weights can be tuned per application

## Use Cases

- **Enterprise Search**: Mix of keywords and concepts
- **E-commerce**: Product names + semantic features
- **RAG Systems**: Better document retrieval for LLMs
- **Legal/Medical**: Specific terms + conceptual queries
- **Customer Support**: Ticket routing and KB search

## Implementation Examples

Major platforms supporting hybrid search:
- Weaviate (native hybrid search with alpha parameter)
- Elasticsearch (hybrid scoring)
- OpenSearch (with RRF)
- Qdrant (hybrid search mode)
- Pinecone (sparse-dense hybrid)

## Best Practices

- Start with equal weights, then tune based on data
- Use RRF for simplicity and robustness
- Consider query type (keyword-heavy vs conceptual)
- Test with representative queries
- Monitor both BM25 and vector contributions

## Pricing

Implementation varies by vector database platform.