## Overview

Context window strategies address the challenge of fitting retrieved information into LLM token limits while maintaining quality. With typical limits of 4K-128K tokens, strategic selection and compression are essential for effective RAG.

## The Context Window Problem

### Constraints
- LLM context limits: 4K (GPT-3.5), 8K, 16K, 32K, 128K+ (Claude, GPT-4)
- Must fit: System prompt + Retrieved docs + Query + Response buffer
- More context != better (lost in the middle problem)

## Core Strategies

### 1. Retrieval Limitation
Retrieve fewer, more relevant documents:
- Top-k selection (3-10 docs typical)
- Reranking for quality
- Diversity filtering
- Redundancy removal

### 2. Chunk Size Optimization
Balance detail vs quantity:
- Smaller chunks: More docs, less context each
- Larger chunks: Fewer docs, more context each
- Typical: 512-1024 tokens per chunk

### 3. Hierarchical Retrieval
Multi-stage approach:
- Retrieve with small chunks (precise)
- Return parent chunks (more context)
- Best of both worlds

### 4. Summarization
Compress retrieved content:
- Summarize each chunk
- Extract only relevant portions
- Use extraction LLM first
- Trade processing time for tokens

### 5. Iterative Retrieval
Multiple rounds:
- Initial retrieval
- LLM generates follow-up queries
- Additional targeted retrieval
- Refine context iteratively

## Advanced Techniques

### Lost in the Middle Mitigation
Research shows LLMs miss info in middle of context:
- Place most relevant at start and end
- Reorder by importance
- Consider removing middle-ranked items

### Contextual Compression
LangChain's approach:
- Pass chunks through compressor LLM
- Extract only query-relevant sentences
- Significantly reduce token usage
- Maintain critical information

### Sliding Window
For long documents:
- Retrieve relevant sections
- Combine with surrounding context
- Maintain narrative flow
- Handle cross-section references

### Multi-Vector Retrieval
Retrieve at multiple granularities:
- Summary vectors (fast, broad)
- Detailed chunk vectors (precise)
- Choose based on query complexity

## Implementation Patterns

### Token Budget Allocation
Typical RAG context breakdown:
- System prompt: 100-500 tokens
- User query: 50-200 tokens
- Retrieved context: 2000-4000 tokens
- Response buffer: 500-2000 tokens
- Safety margin: 10-20%

### Dynamic Adjustment
Adapt based on query:
- Simple queries: Fewer chunks
- Complex queries: More context
- Monitor context usage
- Fail gracefully if exceeded

## Tools & Libraries

### LangChain
- ContextualCompressionRetriever
- ParentDocumentRetriever
- MultiQueryRetriever
- Token counting utilities

### LlamaIndex
- Context window management
- Hierarchical retrievers
- Automatic summarization
- Response synthesis modes

## Best Practices

1. **Measure Token Usage**: Count accurately
2. **Test Context Limits**: Find optimal k
3. **Use Reranking**: Quality over quantity
4. **Monitor Performance**: Track context overflow
5. **Implement Fallbacks**: Handle edge cases
6. **Document Choices**: Explain strategy to users

## Common Pitfalls

### Context Overflow
- Monitor total tokens
- Implement hard limits
- Truncate gracefully

### Information Loss
- Too aggressive compression
- Test answer quality
- Balance tokens vs completeness

### Performance Impact
- Summarization adds latency
- Multiple retrievals slower
- Cache when possible

## Pricing

LLM costs scale with context token usage.