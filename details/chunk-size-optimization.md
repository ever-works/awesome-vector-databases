## Overview

Chunk size optimization involves finding the ideal length of text segments to embed and store in vector databases. This critically impacts both retrieval quality and the effectiveness of RAG systems.

## Why Chunk Size Matters

### Too Large (>1024 tokens)
- ✗ Less precise retrieval
- ✗ Multiple topics per chunk
- ✗ Exceeds context windows
- ✗ Dilutes relevant information
- ✓ Preserves more context

### Too Small (<128 tokens)
- ✗ Loses important context
- ✗ May split key information
- ✗ More chunks = slower search
- ✗ Incomplete semantic units
- ✓ More precise matching

## Common Chunk Sizes

### By Use Case

**Short Form (256-512 tokens)**
- Q&A pairs
- Product descriptions
- Social media posts
- News snippets

**Medium Form (512-1024 tokens)**
- Documentation paragraphs
- Blog post sections
- Research paper paragraphs
- Most general-purpose RAG

**Long Form (1024-2048 tokens)**
- Detailed technical docs
- Legal documents
- Long-form articles
- When context is critical

## Chunking Strategies

### Fixed Size
- Split every N tokens
- Simple and fast
- May break sentences
- Use with overlap (10-20%)

### Semantic Chunking
- Split at natural boundaries
- Sentence/paragraph level
- Better coherence
- More complex logic

### Recursive Chunking
- Try to split at sentences
- Fall back to tokens if needed
- LangChain's RecursiveCharacterTextSplitter

### Document Structure
- Split by headers/sections
- Preserve hierarchy
- Best for structured docs
- Examples: Markdown, HTML

## Overlap Considerations

### Chunk Overlap
Add overlap between chunks:
- Typical: 10-20% (50-200 tokens)
- Prevents information loss at boundaries
- Helps capture context spanning boundaries
- Trade-off: More storage, better retrieval

## Optimization Process

1. **Start with Standard**: 512 tokens, 50 overlap
2. **Measure Baseline**: Retrieval accuracy metrics
3. **Test Variations**: 256, 512, 1024 tokens
4. **Evaluate**: Use eval dataset with known relevant chunks
5. **Monitor**: NDCG, MRR, recall@k
6. **Iterate**: Adjust based on results

## Evaluation Metrics

- **Hit Rate**: % queries finding relevant chunks
- **MRR (Mean Reciprocal Rank)**: Position of first relevant result
- **NDCG@k**: Quality of top-k results
- **Context Relevance**: LLM-judged quality
- **Answer Accuracy**: End-to-end RAG performance

## Advanced Techniques

### Adaptive Chunking
- Different sizes for different doc types
- Code: smaller chunks
- Narrative: larger chunks

### Hierarchical Chunking
- Multiple chunk sizes
- Parent-child relationships
- Retrieve small, return large

### Late Chunking
- Embed full document
- Chunk the embeddings (Jina AI approach)
- Maintains global context

### Agentic Chunking
- LLM-determined boundaries
- Content-aware splitting
- Higher quality, more expensive

## Model Considerations

### Embedding Model Limits
- Check max_seq_length
- Common: 512 tokens (BERT-based)
- New models: 8192+ tokens
- Truncation vs splitting

### LLM Context Windows
- Ensure chunks fit in final context
- Consider multiple chunks
- Reserve space for instruction, query

## Best Practices

1. **Test with Your Data**: Generic advice varies
2. **Consider Domain**: Technical vs narrative
3. **Measure Impact**: A/B test chunk sizes
4. **Use Overlap**: 10-20% typical
5. **Document Structure**: Respect natural boundaries
6. **Iterate**: Optimize based on metrics

## Tools & Libraries

- **LangChain**: RecursiveCharacterTextSplitter
- **LlamaIndex**: Various chunking strategies
- **Haystack**: DocumentSplitter
- **Semantic Kernel**: TextChunker

## Pricing

Processing and storage costs scale with number of chunks.