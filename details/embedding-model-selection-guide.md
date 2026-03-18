## Model Selection Criteria

Choosing the right embedding model impacts retrieval quality, costs, and system performance.

## Key Factors

**1. Performance (MTEB Score)**:
- General benchmark performance
- Task-specific metrics
- Domain relevance

**2. Cost**:
- API pricing (if using hosted)
- Inference costs (if self-hosted)
- Model size

**3. Latency**:
- Model size affects speed
- Batch processing capability
- Hardware requirements

**4. Context Length**:
- How much text can be embedded
- 512 vs 8192 tokens

**5. Dimensions**:
- Storage implications
- Performance trade-offs

## Model Categories

**General Purpose**:
- OpenAI text-embedding-3-small/large
- Cohere Embed v3/v4
- voyage-3
- all-MiniLM-L6-v2 (lightweight)
- BGE-base/large

**Domain-Specific**:
- Medical: PubMedBERT
- Legal: Legal-BERT
- Code: CodeBERT
- Scientific: SciBERT

**Multilingual**:
- voyage-multilingual-3
- multilingual-e5-large
- LaBSE
- paraphrase-multilingual

**Long Context**:
- jina-embeddings-v3 (8K tokens)
- Nomic Embed (8K tokens)

## Top Performers (2026)

**Best Overall**: voyage-4, Cohere Embed v4
**Best Open-Source**: BGE-M3, jina-embeddings-v3
**Best Budget**: all-MiniLM-L6-v2, text-embedding-3-small
**Best Multimodal**: voyage-multimodal-3.5

## Selection by Use Case

**General RAG**:
- OpenAI text-embedding-3-small (cost/performance)
- voyage-3 (best quality)

**Code Search**:
- CodeBERT
- OpenAI text-embedding-3 (surprisingly good)

**Multilingual**:
- voyage-multilingual-3
- multilingual-e5

**Long Documents**:
- jina-embeddings-v3
- Nomic Embed

**Budget-Conscious**:
- all-MiniLM-L6-v2 (self-host)
- text-embedding-3-small (API)

## Evaluation Methodology

1. **Benchmark on MTEB**: Standard comparison
2. **Test on Your Data**: Critical!
3. **Measure Retrieval Quality**: Recall@K
4. **Check Latency**: In production conditions
5. **Calculate Costs**: Storage + compute

## Fine-Tuning Considerations

**When to Fine-Tune**:
- Specialized domain
- Available labeled data
- Base models underperform

**When Not To**:
- General use case
- Limited data
- Good base model exists

## Cost Comparison

(Per 1M tokens)
- OpenAI text-embedding-3-small: $0.02
- OpenAI text-embedding-3-large: $0.13
- Cohere Embed v3: $0.10
- voyage-3: $0.06
- Self-hosted: GPU costs only

## Migration Strategy

If changing models:
1. Re-embed all documents
2. Test retrieval quality
3. Gradual rollout
4. Monitor metrics
5. Keep old index temporarily

## Best Practices

1. Start with good general model
2. Test on your specific data
3. Consider total cost of ownership
4. Plan for model updates
5. Monitor performance over time
6. Don't over-optimize early
7. Use latest model versions