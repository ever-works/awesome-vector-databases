## Overview

Asymmetric search recognizes that queries and documents have different characteristics: queries are typically short (3-10 words) while documents are long (100-1000s of words). Some embedding models optimize for this asymmetry.

## Query vs Document

**Query**: "best pizza recipe"
- Short
- Keyword-like  
- User intent
- Natural language questions

**Document**: Full recipe with ingredients, instructions, tips
- Long
- Complete information
- Structured content

## Asymmetric Models

Models like Sentence-BERT can be trained with different encoders or prompts for queries vs documents:

```python
# Some models use prefixes
query_embedding = model.encode("query: best pizza recipe")
doc_embedding = model.encode("passage: [full recipe text]")
```

## Benefits

- Better matching of short queries to long documents
- Optimized for search use case
- Improved recall

## Contrast with Symmetric

**Symmetric**: Document-to-document similarity (clustering)
**Asymmetric**: Query-to-document search (retrieval)

## Model Examples

- INSTRUCTOR embeddings (instruction-based)
- Cohere embed-english-v3 (search-optimized)
- Some Sentence-BERT configurations

## Pricing

Not applicable (search paradigm).