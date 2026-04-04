## Overview

Galileo is an evaluation and observability platform designed for build and optimizing RAG (Retrieval-Augmented Generation) systems. It provides tools to evaluate various components of a RAG pipeline including embedding models, rerankers, retrievers, and LLM outputs.

## Features

- **Embedding Model Evaluation**: Compare and benchmark different embedding models (e.g., OpenAI text-embedding-3-small vs. HuggingFace models) using retrieval metrics
- **Reranker Evaluation**: Test different reranking configurations (emb_k, rerank_k) to measure improvements in attribution and context adherence
- **Attribution Analysis**: Trace which retrieved chunks are attributed to generated answers, enabling granular error analysis
- **Context Adherence Scoring**: Measure reduction in hallucinations by evaluating how well generated answers stick to provided context
- **Pipeline Observability**: Comprehensive monitoring across the entire RAG pipeline, from retrieval through generation
- **Sweep Experiments**: Run parameter sweeps across embedding models, dimensions, LLM models, and retrieval/reranking parameters
- **Individual Run Inspection**: Analyze individual runs to identify which chunks were attributed and their attribution scores

## Evaluation Metrics

- **Attribution**: Measures how relevant retrieved chunks are for addressing the question (e.g., 10% improvement observed with Cohere reranker)
- **Context Adherence**: Tracks reduction in hallucinations by measuring adherence to provided context (e.g., 5% improvement with reranking)
- **Retrieval Metrics**: Standard IR metrics like NDCG for evaluating reranker effectiveness

## RAG Pipeline Components Supported

- Vector store integration (Pinecone and others)
- Contextual compression retrievers
- Language model integration (OpenAI GPT-3.5, GPT-4, etc.)
- Embedding model comparison
- Reranker evaluation (Cohere, custom rerankers)

## Pricing

Free tier available to get started.