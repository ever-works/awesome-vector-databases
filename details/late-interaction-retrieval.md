## Overview

Late Interaction Retrieval is a retrieval paradigm where query and document encodings are computed independently and kept separate until a "late interaction" stage. This contrasts with traditional dense retrieval where queries and documents are encoded into single vectors.

## How It Works

### Multi-Vector Representations

Instead of encoding text into a single vector:
1. Each token in the query gets its own vector
2. Each token in the document gets its own vector
3. Similarity is computed through token-level interactions

### MaxSim Operation

The key operation in late interaction is MaxSim:
- For each query token vector, find the maximum cosine similarity with all document token vectors
- Sum these maximum similarities across all query tokens
- Results in the final relevance score

## Key Advantages

- **Expressive Representations**: Maintains fine-grained semantic information
- **Offline Indexing**: Document representations can be pre-computed
- **Fast Retrieval**: Efficient similarity computation at query time
- **Better Quality**: Often outperforms single-vector approaches

## Models Using Late Interaction

- **ColBERT**: Original late interaction model for text retrieval
- **ColPali**: Extends to multimodal document retrieval
- **ColQwen**: Qwen-based multimodal retrieval
- **Jina-ColBERT v2**: Production-optimized variant

## Use Cases

- High-quality document retrieval
- Multimodal search (text + images)
- Complex document understanding
- RAG systems requiring nuanced retrieval
- Enterprise search applications

## Trade-offs

- Higher storage requirements than single-vector approaches
- More complex implementation
- Requires specialized indexing strategies

## Implementation

Major vector databases supporting late interaction:
- Vespa (with MaxSim operator)
- Qdrant (late interaction support)
- Weaviate (ColBERT integration)

## Pricing

Concept implementations vary; models and databases have individual pricing.