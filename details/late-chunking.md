## What is Late Chunking?

Late chunking is a technique where you embed the entire document first with a long-context embedding model, then chunk the resulting contextualized representations, rather than chunking text first then embedding each chunk independently.

## Traditional Chunking Problem

**Standard Approach**:
1. Split document into chunks (500 tokens)
2. Embed each chunk independently
3. Store chunk embeddings

**Issues**:
- Context loss at boundaries
- Chunks lack full document context
- Related information split
- Lower retrieval quality

## Late Chunking Process

1. **Embed Full Document**: Use long-context model (8K+ tokens)
2. **Get Token Embeddings**: Each token has contextualized embedding
3. **Chunk After Embedding**: Split token embeddings
4. **Pool Chunk Embeddings**: Average or max pool
5. **Store**: Chunks with full context

## Advantages

**Better Context**:
- Each chunk knows about entire document
- Cross-reference awareness
- Section relationships preserved

**Improved Retrieval**:
- 5-10% better recall
- Especially for technical docs
- Better handling of references

**Semantic Coherence**:
- "It" and "they" properly contextualized
- Forward/backward references resolved
- Better pronoun handling

## When to Use

**Best For**:
- Technical documentation
- Academic papers
- Legal documents
- Documents with cross-references
- Long-form content

**Not Needed For**:
- Short documents
- Independent chunks
- Simple content
- No cross-references

## Requirements

**Long-Context Model**:
- jina-embeddings-v3 (8K)
- Nomic Embed (8K)
- voyage-3 (16K)
- Must support long contexts

**Implementation Support**:
- Requires model API supporting token-level embeddings
- Custom chunking logic
- More complex than standard

## Implementation Example

```python
# With Jina Embeddings v3
from transformers import AutoModel

# 1. Get token embeddings for full doc
token_embeddings = model.encode(
    full_document,
    return_dense=True,
    return_sparse=False,
    return_colbert_vecs=True  # Token-level
)

# 2. Define chunk boundaries (tokens)
chunk_boundaries = [(0, 512), (512, 1024), ...]

# 3. Pool token embeddings per chunk
chunk_embeddings = [
    pool(token_embeddings[start:end])
    for start, end in chunk_boundaries
]

# 4. Store with full context
for i, emb in enumerate(chunk_embeddings):
    store(chunk_text[i], emb)
```

## Performance Impact

**Pros**:
- Better retrieval quality
- Improved context understanding
- Worth the complexity for quality-critical apps

**Cons**:
- More computation (embed full doc)
- Requires long-context model
- Implementation complexity
- Limited model support

## Comparison to Alternatives

**vs Standard Chunking**:
- Late: Better context, more complex
- Standard: Simpler, faster, context loss

**vs Sliding Window**:
- Late: No overlap needed
- Sliding: Redundant storage

**vs Hierarchical**:
- Late: Single-level, contextual
- Hierarchical: Multi-level, summarized

## Best Practices

1. Use with long-context models only
2. Test on your document type
3. Compare vs standard chunking
4. Monitor computational cost
5. Combine with other techniques
6. Document chunking strategy

## Supported Frameworks

- **Jina AI**: Native support
- **LlamaIndex**: Experimental
- **LangChain**: Custom implementation
- **Direct**: Model API + custom code

## Future Development

Late chunking is gaining traction as:
- More long-context models available
- Better tooling support
- Quality benefits proven
- Implementation simplifies

## Measuring Impact

**Compare**:
1. Standard chunking recall@10
2. Late chunking recall@10
3. Measure improvement
4. Check computational cost
5. Decide if worth trade-off

Typical improvement: 3-8% better recall on technical documents.