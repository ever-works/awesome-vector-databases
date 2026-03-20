## Overview

INSTRUCTOR is an instruction-finetuned text embedding model that generates domain-specific and task-aware embeddings without any fine-tuning, simply by providing task instructions.

## Key Innovation

Unlike traditional embedding models with fixed representations, INSTRUCTOR computes embeddings based on instructions explaining the use case (e.g., "Represent the Science question for retrieving supporting documents").

## Model Variants

- **hkunlp/instructor-base**: Base model
- **hkunlp/instructor-large**: Larger variant
- **hkunlp/instructor-xl**: Largest model with highest quality

## Performance

State-of-the-art on 70 diverse embedding tasks (MTEB leaderboard)

## Use Cases

- Classification with domain-specific embeddings
- Retrieval optimized for specific document types
- Clustering tailored to domain
- Text evaluation with custom criteria
- Cross-domain transfer without retraining

## Availability

Hugging Face, LangChain, Haystack support