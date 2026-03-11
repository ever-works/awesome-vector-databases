## Overview

Contextual Retrieval is Anthropic's RAG technique that dramatically improves retrieval accuracy by adding chunk-specific context before embedding and indexing.

## The Problem

Traditional RAG splits documents into chunks that may lack sufficient context. Individual chunks might not specify:
- Which entity they reference
- Relevant time periods
- Document context
- Relationships to other content

## Solution

### Two Sub-Techniques

1. **Contextual Embeddings**: Prepend explanatory context (50-100 tokens) before embedding
2. **Contextual BM25**: Add same context before creating BM25 index

### How It Works

Generate chunk-specific contextual text explaining:
- What the chunk discusses
- Its relationship to the broader document
- Key entities and their context
- Temporal information

## Performance Improvements

- **Contextual Embeddings alone**: 35% reduction in failed retrievals (5.7% → 3.7%)
- **Contextual Embeddings + Contextual BM25**: 49% reduction (5.7% → 2.9%)
- **With Reranking**: 67% reduction (5.7% → 1.9%)

## When to Use

Ideal for knowledge bases larger than 200,000 tokens (~500 pages). Smaller knowledge bases can be included entirely in prompts.

## Implementation

Supported in:
- Amazon Bedrock Knowledge Bases
- Together AI
- Custom RAG pipelines
- Various frameworks with Claude integration

## Pricing

Technique available for free implementation. Costs associated with LLM calls for context generation and vector database storage.