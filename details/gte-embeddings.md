## Overview

The GTE (General Text Embeddings) models are trained by Alibaba DAMO Academy and are mainly based on the BERT framework. They are trained on a large-scale corpus of relevance text pairs, covering a wide range of domains and scenarios.

## Model Sizes

GTE offers three different sizes to balance performance and efficiency:
- **GTE-large**: Highest performance
- **GTE-base**: Balanced performance and size
- **GTE-small**: Optimized for efficiency (MTEB score: 61.36)

## Benchmark Performance

GTE models were compared with other popular text embedding models on the MTEB benchmark:
- Detailed comparison results available on MTEB leaderboard
- GTE-small achieves comprehensive score of 61.36 on MTEB
- Competitive performance across various embedding tasks

## Recent Developments

### GTE-v1.5 Series
Upgraded GTE embeddings with:
- Support for context length up to 8192 tokens
- Enhanced model performance
- Built upon transformer++ encoder backbone (BERT + RoPE + GLU)

### GTE-Multilingual (mGTE) Series
Introduced by Alibaba's Tongyi Lab featuring:
- High performance across languages
- Long-context handling
- Multilingual support
- Elastic embedding capabilities
- Significantly improved retrieval and ranking efficiency
- Outstanding results across datasets

## Applications

GTE models enable various downstream tasks:
- Information retrieval
- Semantic textual similarity
- Text reranking
- RAG (Retrieval-Augmented Generation) systems
- Cross-lingual search

## Technical Details

- Based on BERT framework
- Trained on diverse relevance text pairs
- Covers wide range of domains and scenarios
- Supports both English and multilingual variants

## Availability

- Hugging Face Model Hub
- DeepInfra deployment platform
- Various cloud inference services
- Open-source with permissive licensing

## Evolution Path

1. **Original GTE**: BERT-based, standard context
2. **GTE-v1.5**: Extended context (8192), transformer++ backbone
3. **GTE-Multilingual**: Multilingual support, elastic embeddings
4. **GTE-Qwen**: Next-generation models based on Qwen foundation

## Comparison with Competitors

GTE models provide strong performance while maintaining efficiency, making them suitable for production deployments where both quality and resource constraints matter.