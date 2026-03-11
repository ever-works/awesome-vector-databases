## Overview

Chunking strategies determine how documents are split before embedding, critically impacting RAG system performance.

## Common Strategies

### Fixed-Size Chunking

- **Simple**: Split by character/token count
- **Fast**: Low overhead
- **Limitation**: May break semantic units

### Recursive Character Splitting

- **Hierarchical**: Try multiple separators
- **Smart**: Respects document structure
- **Popular**: LangChain's RecursiveCharacterTextSplitter

### Semantic Chunking

- **Meaning-Based**: Split at topic boundaries
- **Contextual**: Preserves semantic units
- **Better Retrieval**: More coherent chunks

### Sentence/Paragraph-Based

- **Natural Units**: Respect linguistic boundaries
- **Balanced**: Good context vs granularity

## Key Considerations

### Chunk Size

- **Small (128-256 tokens)**: Precise retrieval, may lack context
- **Medium (512-1024 tokens)**: Balanced approach
- **Large (1024-2048 tokens)**: Rich context, less precise

### Chunk Overlap

- **Typical**: 10-20% overlap
- **Benefit**: Preserves context across boundaries
- **Tradeoff**: Slight redundancy

## Best Practices

- Match chunk size to embedding model context window
- Test different strategies for your data
- Consider document structure
- Balance precision and context

## Tools

- LangChain text splitters
- LlamaIndex node parsers
- Unstructured.io
- Custom implementations

## Pricing

Strategies, not products.