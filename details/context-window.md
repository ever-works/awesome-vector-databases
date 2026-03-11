## Overview

Context window refers to the maximum number of tokens a model can process in a single input. For embedding models, it determines how much text can be encoded at once. For LLMs in RAG, it affects how much retrieved context can be used.

## Importance in Vector Databases

### Chunking Strategy
Context window directly impacts chunking decisions:
- Small windows (512 tokens): Require smaller chunks
- Medium windows (2048 tokens): Allow paragraph-level chunks
- Large windows (8192+ tokens): Can encode entire documents

### RAG Applications
Larger context windows enable:
- Fewer chunks per document
- Better semantic coherence
- Reduced retrieval complexity
- More accurate responses

## Modern Context Windows (2026)

### Embedding Models
- **Small**: 512 tokens (older models)
- **Standard**: 2048-4096 tokens (most current models)
- **Long**: 8192 tokens (Jina, Nomic v2, Voyage)
- **Ultra-long**: 32,000+ tokens (specialized models)

### LLMs for RAG
- **Standard**: 4K-8K tokens
- **Extended**: 32K-128K tokens (Claude, GPT-4)
- **Long**: 200K+ tokens (Claude 2.1, Gemini 1.5)

## Trade-offs

### Longer Windows
**Advantages:**
- Encode more context
- Fewer chunks needed
- Better document-level understanding

**Disadvantages:**
- Higher computational cost
- Slower inference
- Potential attention dilution

## Best Practices

- Match chunk size to model's context window
- Leave buffer for query tokens in retrieval
- For long documents, consider hierarchical chunking
- Test different sizes for your use case
- Consider computational costs

## Recent Trends (2026)

- Most embedding models support 8K+ tokens
- RAG systems leveraging 100K+ context LLMs
- Trade-off between context length and cost
- Matryoshka embeddings enabling flexible lengths

## Impact on Vector Database Design

Context window affects:
- Optimal chunk sizes (typically 400-512 tokens for 2K window)
- Overlap strategies (10-20% of window)
- Retrieval strategies (top-k selection)
- Storage requirements