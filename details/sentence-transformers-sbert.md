## Overview

SBERT is the go-to Python module for accessing, using, and training state-of-the-art embedding and reranker models. Sentence-BERT (SBERT) is a modification of the pretrained BERT network that uses siamese and triplet network structures to derive semantically meaningful sentence embeddings.

## Architecture

SBERT implements an additional pooling layer on top of BERT, enabling the model to produce fixed-size sentence embeddings that can be compared using cosine similarity without requiring inference computation for every sentence-pair comparison.

## Key Features

- **15,000+ Pre-trained Models**: Available on 🤗 Hugging Face
- **Semantic Embeddings**: Generate dense vector representations for sentences
- **Fast Comparison**: Cosine similarity for sentence-pair comparison
- **Multiple Tasks**: Semantic search, similarity, clustering, reranking
- **Easy to Use**: Simple Python API

## Performance

SBERT outperformed the previous state-of-the-art (SOTA) models for all common semantic textual similarity (STS) tasks, achieving significantly better performance while being much faster than computing BERT representations for every pair.

## Applications

- Semantic search
- Semantic textual similarity
- Paraphrase mining
- Text clustering
- Document classification
- Question answering

## Model Categories

- **Text Embedding Models**: For semantic search and similarity
- **Cross-Encoders**: For reranking and classification
- **Multilingual Models**: Support for 100+ languages
- **Domain-Specific Models**: Fine-tuned for specific domains

## Popular Models

- all-MiniLM-L6-v2: Fast and efficient
- all-mpnet-base-v2: Best quality
- paraphrase-multilingual: Multilingual support
- MS MARCO models: Trained for search

## Installation

```bash
pip install sentence-transformers
```

## Basic Usage

```python
from sentence_transformers import SentenceTransformer
model = SentenceTransformer('all-MiniLM-L6-v2')
embeddings = model.encode(['First sentence', 'Second sentence'])
```

## Integration

- Hugging Face
- LangChain
- LlamaIndex
- Haystack
- Vector databases

## Research Foundation

**Paper**: "Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks" (2019)
ArXiv: https://arxiv.org/abs/1908.10084

## Resources

- GitHub: https://github.com/huggingface/sentence-transformers
- Documentation: https://sbert.net/
- PyPI: https://pypi.org/project/sentence-transformers/

## Pricing

Free and open-source under Apache 2.0 license.