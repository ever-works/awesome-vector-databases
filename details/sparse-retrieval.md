## Overview

Sparse retrieval represents documents and queries as high-dimensional sparse vectors where most elements are zero. Traditional methods like BM25 and TF-IDF create sparse representations based on term frequencies, while modern neural approaches like SPLADE learn sparse vectors.

## Traditional Sparse Methods

### BM25 (Best Matching 25)
- Most popular sparse ranking function
- Considers term frequency and document length
- Probabilistic retrieval framework
- Default in Elasticsearch and most search engines
- Formula accounts for:
  - Term frequency in document
  - Inverse document frequency
  - Document length normalization

### TF-IDF
- Term Frequency × Inverse Document Frequency
- Simpler than BM25
- Still widely used
- Foundation for many IR systems

## Neural Sparse Retrieval

### SPLADE (Sparse Lexical And Expansion)
- Learns sparse vectors with neural networks
- Term weighting: adjusts importance of words
- Term expansion: adds related terms not in text
- Compatible with inverted indexes
- Performance competitive with dense methods

### Advantages of Neural Sparse
- Semantic understanding via term expansion
- Interpretable (can see which terms matter)
- Works with existing inverted index infrastructure
- Faster than dense in some scenarios

## Sparse Vector Characteristics

### Dimensionality
- Size = vocabulary size (10K-100K+)
- Most values are zero (sparse)
- Efficient storage with sparse formats

### Inverted Index
- Maps terms to document IDs
- Only stores non-zero entries
- Enables fast keyword lookup
- Fundamental to search engines

## Advantages

- **Exact Matching**: Finds specific keywords, IDs, names
- **Interpretable**: Can see which terms matched
- **Fast**: Optimized inverted index lookups
- **No Embedding Required**: Works directly with text
- **Established**: Decades of optimization

## Limitations

- **Vocabulary Mismatch**: Misses synonyms, paraphrases
- **No Semantics**: Doesn't understand meaning
- **Language Specific**: Each language needs separate handling
- **Rare Terms**: Struggles with low-frequency words

## Use Cases

- **Exact Keyword Search**: Product codes, IDs, names
- **Legal/Medical**: Specific terminology matters
- **Code Search**: Function/variable names
- **Hybrid Search**: Combined with dense retrieval
- **Filtering**: Narrow down before dense reranking

## Hybrid Sparse + Dense

Combining both approaches:
- BM25 for exact keyword matching
- Dense vectors for semantic similarity
- Reciprocal Rank Fusion to merge
- Best overall retrieval quality

## Implementation

### Traditional Sparse
- Elasticsearch (BM25)
- Apache Solr (TF-IDF, BM25)
- Whoosh (Python)
- Tantivy (Rust)

### Neural Sparse
- SPLADE models
- Pinecone (sparse-dense hybrid)
- OpenSearch (hybrid search)
- Custom implementations

## Performance Optimization

- Index compression
- Term pruning
- Early termination
- Caching frequent queries
- Distributed inverted indexes

## Pricing

Varies by search engine; Elasticsearch/OpenSearch pricing applies.