## Overview

Semantic Chunker is an advanced document splitting strategy that uses embedding models to determine natural breakpoints in text. Unlike fixed-size methods, it creates variable-length chunks based on semantic similarity.

## Features

- **Embedding-Based**: Uses embedding similarity to determine splits
- **Dynamic Boundaries**: Variable chunk sizes based on content
- **Semantic Coherence**: Keeps related content together
- **Context-Aware**: Understands topic transitions
- **Multiple Variants**: LLMSemanticChunker, ClusterSemanticChunker
- **Adaptive**: Adjusts to document structure and content

## Performance (2026)

- LLMSemanticChunker achieved 0.919 recall
- ClusterSemanticChunker reached 0.913 recall
- Vecta benchmark showed 54% accuracy with 43-token average chunks
- Performance varies significantly based on implementation and configuration

## Use Cases

- Content with strong thematic structure
- Documents where topic boundaries matter
- High-value retrieval where cost is justified
- Applications requiring nuanced context preservation
- Technical documentation with clear sections

## Considerations

- **Higher Cost**: Requires embedding generation for chunking
- **Computational Overhead**: More expensive than simple splitting
- **Variable Performance**: Results depend heavily on content type
- **Not Always Better**: Recursive splitting often performs as well or better

## Best Practices

Start with recursive character splitting. Move to semantic chunking only if metrics show you need extra performance and budget allows for the additional costs.

## Integration

Available in LangChain with LLMSemanticChunker and other variants. Also supported in LlamaIndex and other frameworks.

## Pricing

Free algorithmic approach, but incurs embedding API costs for similarity calculations.