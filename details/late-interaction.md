## Overview

Late Interaction is a retrieval paradigm where query and document are encoded independently into multiple vectors (one per token), and their interaction is computed efficiently at search time. This approach bridges the gap between fast bi-encoders and accurate cross-encoders.

## How Late Interaction Works

### Encoding Phase

1. Encode query into multiple token vectors (e.g., 32 tokens → 32 vectors)
2. Encode document into multiple token vectors (e.g., 180 tokens → 180 vectors)
3. Store document vectors in index

### Retrieval Phase

1. For each query token vector, find its maximum similarity with any document token vector
2. Sum these maximum similarities across all query tokens
3. This computes the query-document relevance score

## Key Advantages

### Better Than Bi-Encoders

- Captures fine-grained token-level interactions
- Higher accuracy for complex queries
- Better handling of multi-aspect queries

### Faster Than Cross-Encoders

- Pre-compute document representations
- No need to encode query-document pairs at search time
- Can leverage vector search infrastructure

## ColBERT: Popular Implementation

ColBERT (Contextualized Late Interaction over BERT) is the most well-known late interaction model:
- Produces 128-dim vectors per token
- Uses MaxSim operator for scoring
- Achieves state-of-the-art results

## Performance Characteristics

- **Accuracy**: Between bi-encoders and cross-encoders
- **Speed**: Much faster than cross-encoders
- **Storage**: More than single-vector bi-encoders (multiple vectors per document)

## Modern Applications

- ColPali for visual document retrieval
- ColBERT for text retrieval
- Multimodal late interaction models
- RAG systems requiring high precision

## Storage Considerations

Stores multiple vectors per document:
- 200-word document → ~180 token vectors
- Requires more storage than single-vector embeddings
- Often compressed using quantization

## Use Cases

- High-precision retrieval
- Long document search
- Multi-aspect queries
- When accuracy matters more than storage

## Pricing

Implemented in open-source libraries (ColBERT, RAGatouille, etc.)