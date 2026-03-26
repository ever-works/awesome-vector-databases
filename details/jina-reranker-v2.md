## Overview

The Jina Reranker v2 (jina-reranker-v2-base-multilingual) is a transformer-based model that has been fine-tuned for text reranking task, which is a crucial component in many information retrieval systems.

## Architecture

It is a cross-encoder model that takes a query and a document pair as input and outputs a score indicating the relevance of the document to the query. The model employs a cross-encoder architecture enhanced with Flash Attention 2, enabling direct comparison between queries and documents for more accurate relevance assessment.

## Key Capabilities

### Multilingual Support
Features function-calling support, multilingual retrieval for over 100 languages, code search capabilities, and offers a 6x speedup over v1.

### Performance
The model reaches state-of-the-art performance in accuracy with only 278M parameters. Compared to bge-reranker-v2-m3 with 567M parameters, Jina Reranker v2 is only half the size.

### Long Text Handling
The model is capable of handling long texts with a context length of up to 1024 tokens, and uses a sliding window approach to chunk the input text into smaller pieces and rerank each chunk separately for texts exceeding this limit.

## Benchmark Performance

The Jina Reranker v2 model has demonstrated competitiveness across a series of benchmarks targeting text retrieval, multilingual capability, function-calling-aware and text-to-SQL-aware reranking, and code retrieval tasks.

## Integration & Availability

The model is available on Hugging Face and can be integrated with frameworks like sentence-transformers, LangChain, and Haystack, or accessed via Jina AI's Reranker API.

## Use Cases

- Agentic RAG applications
- Multilingual search systems
- Code search and retrieval
- Function-calling systems
- Text-to-SQL applications

## Pricing

Available through Jina AI's API with consumption-based pricing.