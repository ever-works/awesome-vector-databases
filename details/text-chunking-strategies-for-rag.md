## Overview

Chunking is the process of breaking down large documents into smaller, manageable pieces for vector embedding and retrieval. The right chunking strategy directly impacts retrieval accuracy, context preservation, and overall RAG system performance.

## Main Chunking Strategies

### 1. Fixed-Size Chunking

**Description**: Split text with a specific chunk size and optional overlap

**Characteristics**:
- Simple to implement
- Predictable token counts
- May split sentences/paragraphs awkwardly

**Recommended Sizes**: 200-500 tokens with 10-20% overlap

### 2. Recursive Chunking

**Description**: Iterate through separators until achieving preferred chunk size

**Process**:
1. Try splitting on paragraphs (\n\n)
2. If chunks too large, split on sentences
3. If still too large, split on words
4. Final fallback: character-level splitting

### 3. Semantic Chunking

**Description**: Group sentences based on semantic similarity of embeddings

**Advantages**:
- Preserves topical coherence
- Natural content boundaries
- Better context retention

**Disadvantages**:
- Computationally expensive
- Variable chunk sizes

### 4. Document-Based Chunking

**Description**: Split based on document structure

**Methods**:
- Headers and sections
- Paragraphs
- List items
- Table boundaries

## Chunk Overlap

### Why Overlap?

Overlapping chunks mitigate context loss at boundaries:
- Ensures boundary information captured in full
- Provides context from adjacent chunks
- Reduces information fragmentation

### Implementation

**Sliding Window**: Create chunks that share overlapping portions of text
- Begin next chunk before previous one ends
- Duplicate content at edges
- Typical overlap: 10-20% of chunk size

## Recommended Chunk Sizes

| Use Case | Chunk Size | Overlap |
|----------|-----------|----------|
| General RAG | 200-500 tokens | 10-20% |
| Code | 100-300 tokens | 20% |
| Dense technical | 300-600 tokens | 15% |
| Conversational | 150-300 tokens | 10% |

**Starting Point**: 250 tokens (~1000 characters)

## Key Trade-offs

### Smaller Chunks (100-200 tokens)

✓ More accurate retrieval
✓ Specific matching
✗ Less context
✗ May miss connections

### Larger Chunks (500-1000 tokens)

✓ More context
✓ Better comprehension
✗ Less precise retrieval
✗ Higher token costs

## Impact on RAG Performance

**Good Chunking**:
- Improves retrieval precision
- Preserves semantic context
- Reduces hallucinations
- Lowers token usage

**Poor Chunking**:
- Irrelevant retrievals
- Context loss
- Increased hallucinations
- Higher costs

## Best Practices

1. **Experiment**: Test different strategies with your data
2. **Measure**: Track retrieval quality and answer accuracy
3. **Optimize**: Adjust chunk size based on document type
4. **Overlap**: Use moderate overlap (10-20%) for continuity
5. **Metadata**: Include chunk position and source information

## Tools and Libraries

- LangChain: RecursiveCharacterTextSplitter, SemanticChunker
- LlamaIndex: Various chunking strategies
- Unstructured.io: Document-aware chunking
- Haystack: Preprocessing pipelines

## Pricing

Chunking strategies are implementation techniques, free to use.