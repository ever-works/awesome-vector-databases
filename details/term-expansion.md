## Overview

Term Expansion is a retrieval technique that includes alternative but relevant terms beyond those found in the original text. This is what separates modern learned sparse models like SPLADE from traditional keyword search methods like BM25.

## The Problem with Traditional Keyword Search

BM25 can only match terms that literally appear in both the query and the document. If a user searches for "laptop" but the document only mentions "notebook computer", BM25 will miss it.

## How Term Expansion Works

### In SPLADE
1. Transformer model processes the text
2. Generates scores for all vocabulary terms (not just those present)
3. Includes semantically related terms with non-zero weights
4. Creates expanded sparse representation

### Example
Original: "The cat sat on the mat"
Expanded: "cat feline kitty sat rested mat rug carpet"

## Benefits

- **Better Recall**: Finds relevant documents with different terminology
- **Synonym Handling**: Automatically includes synonyms
- **Concept Coverage**: Expands to related concepts
- **Query Understanding**: Interprets user intent beyond literal words
- **Maintains Interpretability**: Still token-based, unlike pure dense vectors

## Comparison: BM25 vs. SPLADE

**BM25**: Only matches exact terms → "laptop" won't match "notebook"
**SPLADE**: Expands terms → "laptop" can match "notebook computer portable"

## Technical Implementation

SPLADE uses:
- BERT-based transformer encoder
- MLM (Masked Language Modeling) head for expansion
- Log-saturation on weights
- FLOPS regularization to control expansion

## Controlled Expansion

Too much expansion → noisy results
Too little expansion → similar to BM25

SPLADE balances this through:
- Regularization techniques
- Training objectives
- Sparsity constraints

## Use Cases

- E-commerce search (product variations)
- Medical literature (terminology variations)
- Legal document search (concept matching)
- Customer support (question variations)
- Cross-domain search

## Performance Impact

Various IR evaluation tasks show SPLADE with term expansion achieves significantly better recall compared to BM25, especially for:
- Semantic similarity
- Synonym matching
- Concept-based retrieval

## Hybrid Approach

Best results combine term expansion (sparse) with dense embeddings:
- Sparse handles exact + expanded terms
- Dense handles semantic similarity
- Complementary strengths

## Implementation Availability

- Qdrant: Native SPLADE support
- Elasticsearch: Sparse vector fields
- Custom implementations with HuggingFace models

## Pricing

Available in various vector databases; costs depend on platform.