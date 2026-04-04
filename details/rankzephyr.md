## Overview

RankZephyr is an open-source reranking model that fine-tunes decoder-only large language models (specifically LLaMA-based architectures) for document reranking tasks. It addresses the lack of ranking awareness in pre-trained LLMs by supervised fine-tuning on task-specific ranking datasets.

## Reranking Approach

- **Listwise Method**: Takes a query and a list of documents as input and instructs the LLM to output reranked document identifiers
- **Sliding Window Strategy**: Due to LLM input length limits, employs a sliding window to rerank subsets of candidate documents at a time, ranking from back to front
- **Supervised Fine-Tuning**: Fine-tuned on ranking datasets such as MS MARCO passage ranking to enable accurate query-document relevance measurement

## Architecture

- **Backbone**: Decoder-only model structure (LLaMA family)
- **Training**: Supervised fine-tuning on passage ranking datasets
- **Comparison**: Alternative to encoder-decoder rerankers like RankT5 that formulate ranking as a classification/generation task

## Use Cases

- RAG pipeline document reranking
- Search result relevance improvement
- Reducing hallucinations in retrieval-augmented generation by prioritizing most relevant context

## Performance

- Outperforms zero-shot LLM-based rerankers without API costs
- More computationally demanding than cross-encoder models but offers competitive effectiveness
- Part of the family of supervised LLM rerankers showing promise for retrieval tasks