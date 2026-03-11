## Overview

Semantic search understands query intent and content meaning, retrieving relevant results based on semantic similarity rather than keyword matching.

## How It Works

1. **Encode**: Convert queries and documents to vector embeddings
2. **Compare**: Compute similarity (typically cosine)
3. **Rank**: Order by relevance
4. **Return**: Top-k most similar results

## vs Keyword Search

### Keyword Search (BM25)
- Exact term matching
- Misses synonyms
- Word-level matching
- Fast and interpretable

### Semantic Search
- Meaning-based matching
- Handles paraphrases
- Context-aware
- Finds conceptually similar content

## Components

- **Embedding Model**: Converts text to vectors
- **Vector Database**: Stores and searches embeddings
- **Similarity Metric**: Measures relevance

## Use Cases

- Document search
- Question answering
- Product recommendations
- Content discovery
- RAG systems

## Best Practices

- Use quality embedding models
- Combine with keyword search (hybrid)
- Fine-tune for domain
- Monitor and iterate

## Pricing

Concept, implemented via embeddings + vector DB.