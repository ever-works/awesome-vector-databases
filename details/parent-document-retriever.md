## Overview

Parent Document Retriever is a RAG technique that separates what you index from what you retrieve. It indexes small, focused chunks for precise matching but returns larger parent documents to provide comprehensive context to the LLM.

## The Problem with Standard Chunking

**Large Chunks**:
- Good context for LLM
- Poor retrieval precision
- May not match specific queries

**Small Chunks**:
- Good retrieval precision
- Insufficient context for LLM
- Missing surrounding information

## Solution: Two-Level Chunking

1. **Index Level**: Small chunks (e.g., 200 tokens)
2. **Retrieval Level**: Parent documents (e.g., 1000 tokens)

When a small chunk matches, return its entire parent document.

## How It Works

### Indexing
```
Parent Doc: [A B C D E F G H I J]
  ↓ split into
Child Chunks: [A B] [C D] [E F] [G H] [I J]
  ↓ embed and index
Vector DB: stores child chunk embeddings with parent doc IDs
```

### Retrieval
```
Query → matches [C D]
  ↓ retrieve parent
Return: [A B C D E F G H I J]
```

## Implementation

```python
from langchain.retrievers import ParentDocumentRetriever
from langchain.text_splitter import RecursiveCharacterTextSplitter

# Child splitter (for indexing)
child_splitter = RecursiveCharacterTextSplitter(chunk_size=200)

# Parent splitter (for retrieval)
parent_splitter = RecursiveCharacterTextSplitter(chunk_size=1000)

retriever = ParentDocumentRetriever(
    vectorstore=vectorstore,
    docstore=docstore,
    child_splitter=child_splitter,
    parent_splitter=parent_splitter,
)
```

## Benefits

- **Better Retrieval**: Small chunks match queries precisely
- **Better Context**: Large parents give LLM full picture
- **Reduced Redundancy**: Deduplication at parent level
- **Flexible**: Tune child/parent sizes independently

## Variants

### Full Document as Parent
- Children: Sentences or paragraphs
- Parent: Entire document
- Best for short documents

### Hierarchical Chunks
- Multiple levels (sentence → paragraph → section)
- Flexible context size
- More complex implementation

## Storage Requirements

- Vectors: Only child chunks (smaller footprint)
- Documents: Both child and parent docs
- Document store: Key-value store for parents

## Trade-offs

**Advantages**:
- Best of both worlds (precision + context)
- Better LLM answers
- Reduced token usage vs. retrieving multiple small chunks

**Costs**:
- More complex implementation
- Need document store in addition to vector DB
- Slightly higher storage

## When to Use

- Documents with clear hierarchical structure
- When small chunks lack context
- When retrieval precision is critical
- Long documents that need chunking

## Pricing

Implementation-dependent. Requires vector DB + document store (can use same database).