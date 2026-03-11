## Overview

FlagEmbedding is a comprehensive retrieval and retrieval-augmented LLM framework developed by the Beijing Academy of Artificial Intelligence (BAAI). It includes the BGE (BAAI General Embedding) series of state-of-the-art embedding models.

## BGE Model Series

### BGE v1.5 (bge-*-v1.5)

Improved version addressing similarity distribution issues:
- Enhanced retrieval ability without requiring instructions
- Available in large, base, and small sizes
- Top performance on MTEB and C-MTEB benchmarks

### BGE-M3 (Multi-Functionality, Multi-Linguality, Multi-Granularity)

The flagship model with unique versatility:

#### Multi-Functionality
- **Dense Retrieval**: Traditional vector similarity search
- **Multi-Vector Retrieval**: Multiple vector representations per document
- **Sparse Retrieval**: Keyword-based retrieval like BM25
- Supports all three retrieval modes simultaneously

#### Multi-Linguality
- Supports over 100 languages
- Trained on balanced multilingual datasets
- Strong cross-lingual capabilities

#### Multi-Granularity
- **Short Texts**: Single sentences
- **Medium Texts**: Paragraphs
- **Long Documents**: Up to 8,192 tokens
- Handles various input lengths effectively

## Training Methodology

- **Pre-training**: RetroMAE approach
- **Fine-tuning**: Large-scale pairs data with contrastive learning
- **Data Quality**: Curated high-quality training datasets

## Additional Models

### Reranker Models

- **bge-reranker-base**: Cross-encoder for reranking
- **bge-reranker-large**: Larger, more powerful reranker
- **bge-reranker-v2-m3**: Latest reranker with multilingual support
- More accurate than embedding-only approaches
- Recommended for re-ranking top-k retrieved documents

## Performance

- **MTEB Leaderboard**: Ranked #1 for English embeddings
- **C-MTEB**: Top performance on Chinese benchmark
- **Multilingual Tasks**: Strong performance across 100+ languages
- **Retrieval Quality**: Superior recall and precision metrics

## Key Features

- **Open Source**: Fully open-source under permissive license
- **Easy Integration**: Compatible with popular frameworks
- **Fine-tuning Support**: Can be adapted to specific domains
- **Production Ready**: Battle-tested in real-world applications

## Use Cases

- Semantic search across languages
- RAG (Retrieval-Augmented Generation) systems
- Document retrieval and ranking
- Clustering and classification
- Cross-lingual information retrieval
- Question answering systems
- Recommendation engines

## Integration

### Framework Support

- LangChain
- LlamaIndex
- Haystack
- HuggingFace Transformers
- Sentence Transformers

### Deployment Options

- Local inference
- Cloud APIs
- Together AI platform
- Amazon Bedrock (fine-tuning support)

## Model Sizes

- **Large**: Maximum accuracy, higher compute
- **Base**: Balanced performance and efficiency
- **Small**: Lightweight, faster inference

## Technical Details

- **Architecture**: Transformer-based encoders
- **Context Window**: Up to 8,192 tokens (BGE-M3)
- **Embedding Dimensions**: Model-dependent (typically 768-1024)
- **Batch Processing**: Optimized for throughput

## Pricing

Free and open-source. Available on HuggingFace Hub for self-hosting or through commercial API providers.