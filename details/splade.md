## Overview

SPLADE (Sparse Lexical and Expansion Model) uses pretrained language models like BERT to identify connections between words/sub-words and uses that knowledge to enhance sparse vector embeddings.

## How SPLADE Works

Unlike dense embeddings, SPLADE outputs vectors aligned with a vocabulary (similar to bag-of-words), but with learned weights reflecting semantic and contextual information.

### Term Expansion Example

For the keyword "study":
- **BM25**: Single non-zero value for "study"
- **SPLADE**: Multiple non-zero values for "study", "learn", "research", "investigate", etc.

## Key Advantages

- **Semantic Understanding**: Leverages context from transformers, improving recall over BM25
- **Term Expansion**: Includes alternative but relevant terms beyond the original sequence
- **Interpretability**: Maintains sparse vector format similar to traditional lexical search
- **Better Recall**: Significantly better performance compared to BM25 in IR evaluation tasks

## Technical Specifications

- **Vector Dimension**: 30,522 (based on BERT vocabulary)
- **Architecture**: Built on BERT transformers
- **Sparsity**: Contains many zero values like traditional sparse vectors, but with learned weights

## SPLADE vs BM25

| Feature | BM25 | SPLADE |
|---------|------|--------|
| Non-zero values | Single term only | Multiple related terms |
| Semantic understanding | None | Yes (via BERT) |
| Term expansion | No | Yes |
| Context awareness | No | Yes |
| Performance | Baseline | Superior recall |

## Use Cases

- Hybrid search (combining with dense vectors)
- Keyword search with semantic understanding
- Entity resolution
- Document retrieval
- Information retrieval systems

## Supported Platforms

- Qdrant
- Pinecone
- Chroma
- Various vector databases with sparse vector support

## Pricing

Open-source model, free to use.