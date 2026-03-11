## Overview

Recursive Character Text Splitter is the most widely recommended chunking strategy for RAG applications in 2026. It uses hierarchical separators to break text at natural boundaries, maintaining semantic coherence.

## Features

- **Hierarchical Splitting**: Uses ["\n\n", "\n", " ", ""] separators in order
- **Natural Boundaries**: Breaks at paragraphs, sentences, and words
- **Configurable Chunk Size**: Typically 400-512 tokens
- **Overlap Support**: 10-20% overlap to maintain context
- **Language Aware**: Can adapt to different document structures
- **Deterministic**: Consistent results for same input

## Best Practices (2026)

- **Recommended Starting Point**: 400-512 tokens with 10-20% overlap
- **Industry Standard**: Most practical default strategy
- **Benchmark Performance**: 69-89.5% accuracy in recent benchmarks
- **Optimal Configuration**: 400 tokens achieves 88.1-89.5% accuracy

## Performance

Vecta's February 2026 benchmark of 7 strategies across 50 academic papers placed recursive 512-token splitting first at 69% accuracy. RecursiveCharacterTextSplitter achieved 85.4-89.5% recall, with best performance at 400 tokens.

## Use Cases

- Default chunking for RAG applications
- Document processing pipelines
- Knowledge base creation
- Long-form content indexing
- General-purpose text splitting

## Comparison

Outperforms semantic chunking in practical benchmarks while being more cost-effective and predictable. Move to semantic or page-level chunking only if metrics show you need extra performance.

## Integration

Available in LangChain, LlamaIndex, and other RAG frameworks. Default choice in most implementations.

## Pricing

Free - it's an algorithmic approach, not a paid service.