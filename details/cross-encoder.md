## Overview

Cross-encoders are neural models that perform full-attention over input pairs, examining both the query and document simultaneously. They achieve higher performance than bi-encoders (like Sentence-BERT) but are more time-consuming.

## How Cross-Encoders Work

Cross-encoders produce an output value between 0 and 1 indicating similarity of sentence pairs, but do not produce sentence embeddings. The model looks at both sentences at once, allowing the interpretation of one sentence to affect the other.

## Architecture

The BERT cross-encoder takes two sentences A and B separated by a [SEP] token as input, with a feedforward layer on top that outputs a similarity score.

## Performance Trade-offs

### Speed

Clustering 10,000 sentences with cross-encoders requires computing about 50 million sentence combinations (taking about 65 hours), while bi-encoders compute embeddings for each sentence in only 5 seconds.

### Accuracy

Cross-encoders achieve higher performance than bi-encoders, however they do not scale well for large datasets.

## Best Practice: Combining Both Approaches

In semantic search scenarios:
1. Use an efficient bi-encoder to retrieve the top-100 most similar sentences
2. Use a cross-encoder to re-rank these 100 hits

This gives you the speed of vector search + the accuracy of cross-encoders. You retrieve 50 chunks fast, rerank to find the best 5, and pass only high-quality context to the LLM.

## Recent Research

Recent findings show that embeddings from earlier layers of cross-encoders can be used within information retrieval pipelines.

## Use Cases

- Reranking in RAG systems
- Semantic similarity assessment
- Question answering
- Information retrieval

## Pricing

Various open-source implementations available (Sentence-Transformers, Hugging Face, etc.)