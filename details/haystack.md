## RAG Integration

Haystack integrates RAG via customizable pipelines: index documents with splitters/embedders, retrieve via hybrid retrievers, rerank candidates, and generate with LLMs, all orchestrated in modular flows.

## Features

- **Chunking**: Overlapping splitters, sentence/embed-aware
- **Retrieval**: Dense (DPR), sparse (BM25), hybrid fusion
- **Rerank**: Cohere, BGE-reranker, cross-encoders
- **Pipelines**: Extractive QA, generative, indexing, evaluation

## Use Cases

- Enterprise semantic search
- Document QA chatbots
- Knowledge-grounded agents
- Multi-lingual RAG apps

## Haystack vs LlamaIndex

| Feature | Haystack | LlamaIndex |
|---------|----------|------------|
| Design | Pipeline nodes | Indexes/Engines |
| Strengths | Modularity, benchmarks | Data connectors, simplicity |
| Maturity | Battle-tested enterprise | Fast-evolving ecosystem |
| Best For | Complex pipelines | Quick RAG setups |

## Pricing

Free open-source (Apache 2.0). Enterprise support via deepset.