## Overview

Hybrid chunking strategies combine multiple chunking approaches to optimize for different document types, structures, and retrieval requirements in RAG systems.

## Common Hybrid Approaches

### Structural + Semantic
Use document structure (headings, paragraphs) as initial boundaries, then apply semantic analysis for fine-grained splits

### Fixed-Size with Overlap + Semantic Boundaries
Default to fixed-size chunks but respect semantic boundaries when they fall within acceptable range

### Hierarchical Chunking
Create both large context chunks and smaller specific chunks, enabling multi-level retrieval

## Best Practices 2026

**Default Recommendation**: Recursive character splitting at 400-512 tokens with 10-20% overlap

**Page-Level**: Best for paginated documents (NVIDIA 2024 benchmark winner)

**Adaptive**: Choose strategy based on document type detection

## Implementation

Major frameworks supporting hybrid chunking:
- LlamaIndex
- LangChain
- Haystack
- Custom implementations

## Use Cases

- Mixed document types (PDFs, web pages, code)
- Enterprise knowledge bases
- Legal/medical documents
- Technical documentation