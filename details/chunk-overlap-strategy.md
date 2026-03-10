## Overview

Chunk overlap is a critical strategy in text chunking where consecutive chunks share 10-20% of their content, preserving context continuity and preventing information loss at chunk boundaries to improve retrieval quality.

## How It Works

- Chunks share overlapping tokens/characters
- Typical overlap: 10-20% of chunk size
- Example: 400-token chunks with 40-80 token overlap
- Sliding window approach
- Maintains context across boundaries

## Why Overlap Matters

### Without Overlap
- Information split across boundaries
- Context loss at chunk edges
- Incomplete retrieval possible
- Semantic meaning fragmented

### With Overlap
- Context preserved across chunks
- Better boundary handling
- Improved retrieval recall
- Semantic continuity maintained

## Benefits

- **Improved Recall**: Critical information not lost at boundaries
- **Better Context**: Each chunk has surrounding context
- **Robust Retrieval**: Multiple chances to find relevant content
- **Semantic Preservation**: Meaning maintained across splits

## Best Practices (2026)

- Use 10-20% overlap as starting point
- 100-token overlap for 400-512 token chunks
- Adjust based on domain and query complexity
- Monitor retrieval metrics
- Balance storage cost vs. quality

## Trade-offs

### Advantages
- Better retrieval quality
- Reduced boundary artifacts
- More robust search

### Costs
- Increased storage (10-20% more vectors)
- Higher embedding costs
- More vectors to search
- Slightly increased latency

## Real-World Results

Financial services firm achieved 12% increase in retrieval accuracy by combining recursive splitting with 100-token overlap.

## When to Use More Overlap

- Complex queries requiring context
- Technical documents with references
- Legal or medical text
- Cross-reference heavy content
- Mission-critical applications

## When to Use Less Overlap

- Cost-sensitive applications
- Simple query patterns
- Well-structured documents
- Large-scale deployments

## Implementation

- Supported in all major chunking libraries
- LangChain: `chunk_overlap` parameter
- LlamaIndex: overlap configuration
- Custom implementations straightforward

## Recommended Settings

- **General Purpose**: 10-15% overlap
- **Technical Docs**: 15-20% overlap
- **Conversational**: 10% overlap
- **Legal/Medical**: 20% overlap

## Monitoring

- Track retrieval quality
- Measure storage impact
- Monitor query latency
- A/B test overlap amounts
- Adjust based on metrics