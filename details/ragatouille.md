## RAG Integration

RAGatouille slots into RAG workflows as retriever/reranker: index docs with ColBERT tokenizer, retrieve top-k via late-interaction scoring, or rerank BM25/embedding results for better precision.

## Features

- **Chunking**: Compatible with any preprocessor
- **Retrieval**: ColBERTv2 (zero-shot strong), multi-token matching
- **Rerank**: Token-level alignment scoring
- **Training**: Fine-tune on domain data

## Use Cases

- High-accuracy RAG apps
- Reranking layer in pipelines
- Zero-shot domain adaptation

## LlamaIndex vs Haystack

RAGatouille complements both as advanced retriever; LlamaIndex integrates easily, Haystack via custom retriever node.

## Pricing

Free open-source (MIT).