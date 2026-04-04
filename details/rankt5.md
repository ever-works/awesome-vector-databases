## Overview

RankT5 is a supervised LLM reranker that employs a T5 encoder-decoder architecture for document reranking. It formulates the ranking problem as a text generation task, outputting classification tokens to indicate relevance.

## Architecture

- **Model Type**: Encoder-decoder (T5) backbone
- **Approach**: Pointwise or pairwise ranking formulation as a generation task
- **Output**: Generates classification tokens (e.g., "relevant" or "irrelevant") for query-document pairs

## Training

- Supervised fine-tuning on passage ranking datasets such as MS MARCO
- Adjusts pre-trained T5 parameters for improved relevance measurement
- Addresses the lack of ranking awareness inherent in pre-trained language models

## Use Cases

- Search result reranking
- RAG pipeline document prioritization
- Semantic relevance scoring for query-passage pairs

## Performance

- Competitive with other LLM-based rerankers on standard benchmarks
- More efficient than listwise LLM reranking methods that require sliding window strategies
- Open-source and can be self-hosted, avoiding API costs