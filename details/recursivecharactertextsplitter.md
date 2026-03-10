## Overview

RecursiveCharacterTextSplitter is LangChain's implementation using a hierarchy of separators to preserve semantic boundaries, recursively splitting text using progressively finer separators until chunks reach target size.

## How It Works

### Separator Hierarchy
Default order: ["\n\n", "\n", " ", ""]
1. Try splitting by paragraphs (\n\n)
2. If chunks too large, split by sentences (\n)
3. If still too large, split by words (" ")
4. If necessary, split by characters ("")

## Performance (2026 Benchmarks)

- Vecta benchmark: 69% accuracy (ranked #1)
- RecursiveCharacterTextSplitter: 85.4-89.5% across tests
- Optimal at 400 tokens: 88.1-89.5% accuracy
- Best at 512 tokens in some academic paper benchmarks

## Key Parameters

- **chunk_size**: Target size in characters/tokens (400-512 recommended)
- **chunk_overlap**: Overlap between chunks (10-20% typical)
- **separators**: Hierarchy of split points
- **length_function**: How to measure chunk size

## Advantages

- Preserves natural text boundaries
- Maintains semantic coherence
- Proven performance in production
- Simple to implement
- Cost-effective
- Well-tested and reliable

## Best Practices (2026)

- Start with 400-512 token chunks
- Use 10-20% overlap
- Default separator order works well
- Monitor retrieval metrics
- Adjust based on domain needs

## When to Use

- General-purpose RAG applications
- Cost-conscious deployments
- Starting point for chunking strategy
- Text with clear paragraph structure
- Production systems requiring reliability

## Comparison with Alternatives

- **vs. Semantic Chunking**: More reliable, lower cost, better accuracy in benchmarks
- **vs. Fixed-size**: Preserves boundaries better
- **vs. Sentence-based**: Better handling of context

## Implementation

- Available in LangChain
- Python implementation
- Easy configuration
- Integration with popular frameworks

## Pricing

Free and open-source (part of LangChain)