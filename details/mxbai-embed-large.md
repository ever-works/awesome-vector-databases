## Overview

mxbai-embed-large is a state-of-the-art large embedding model from mixedbread.ai. It's part of the crispy sentence embedding family from Mixedbread.

## Performance

The model:
- Ranked first among embedding models of similar size
- Outperforms the new OpenAI embedding model, text-embedding-3-large
- Matches the performance of 20x larger models like echo-mistral-7b
- As of March 2024, archives SOTA performance for Bert-large sized models on the MTEB
- Trained with no overlap of the MTEB data, indicating good generalization across domains, tasks and text length

## Training

The model was trained with:
- Over 700 million pairs using contrastive training
- Tuned on over 30 million high quality triplets using the AnglE loss

## Key Features

### Matryoshka Representation Learning

The model supports Matryoshka Representation Learning, allowing vector truncation to smaller dimensions without retraining.

### Binary Quantization

Supports binary quantization for reduced storage and faster similarity search.

### Task-Specific Prompting

For retrieval tasks, you need to provide the prompt "Represent this sentence for searching relevant passages:" for query.

## Technical Specifications

- Suggested maximum sequence length: 512 tokens
- Supports tasks: retrieval, classification, clustering, reranking, and summarization

## Availability

- Hugging Face
- Ollama
- Docker Hub
- Multiple integration platforms

## Pricing

Free and open-source.