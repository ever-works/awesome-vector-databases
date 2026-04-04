## Overview

RankGPT is a reranking approach that leverages decoder-only large language models (LLMs) such as LLaMA to improve document ranking in retrieval systems. It represents one of the supervised LLM reranker methods, where pre-trained LLMs are fine-tuned on ranking-specific datasets like MS MARCO to develop ranking awareness that is absent during standard pre-training.

## Approach

RankGPT formulates document reranking by fine-tuning decoder-only language models. Different from encoder-decoder approaches like RankT5 which generate classification tokens, RankGPT uses decoder-only architectures for relevance calculation. It employs prompting strategies to have LLMs improve document reranking autonomously.

## Reranking Methods

RankGPT can utilize different prompting strategies:

- **Listwise methods**: Rank a list of documents by inserting the query and document list into the prompt and instructing the LLM to output reranked document identifiers. Uses a sliding window strategy due to limited input length of LLMs, ranking from back to front.
- **Pairwise methods**: LLMs receive a prompt with a query and a document pair, then generate the identifier of the more relevant document. Aggregation methods like AllPairs consolidate final relevance scores.
- **Pointwise methods**: Measure relevance between a query and a single document, including relevance generation and query generation subcategories.

## Performance

Zero-shot LLM-based rerankers like RankGPT exhibit competitive effectiveness, with some matching the performance of GPT-3.5 Turbo on various datasets. However, inefficiency and high costs currently limit their practical deployment in production retrieval systems compared to cross-encoder approaches.

## Use Cases

- RAG pipeline reranking in question-answering systems
- Search result reordering based on semantic relevance
- Document ranking for information retrieval tasks

## Limitations

- High computational cost and latency compared to cross-encoder rerankers
- Practical deployment hindered by inefficiency
- Requires significant resources for fine-tuning and inference