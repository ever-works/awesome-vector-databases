## Overview

RAGAS (Retrieval Augmented Generation Assessment) is a framework for evaluating RAG systems without requiring reference answers, using LLM-based judges for quality assessment.

## Key Metrics

**Retrieval Metrics**:
- Context Precision: Relevance of retrieved chunks
- Context Recall: Coverage of relevant information

**Generation Metrics**:
- Faithfulness: LLM answers based on context
- Answer Relevance: Response addresses query

## Reference-Free Evaluation

Unlike traditional metrics requiring ground truth:
- Uses LLMs as judges
- No need for labeled test data
- Evaluates both retrieval and generation

## Use Cases

- Automated RAG quality monitoring
- A/B testing retrieval strategies
- Embedding model selection
- Chunking strategy optimization

## Integration

Supports major frameworks:
- LangChain
- LlamaIndex
- Haystack
- Custom RAG pipelines

## Availability

Open-source Python package

Paper: arXiv:2309.15217