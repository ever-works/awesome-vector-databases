## Overview

Dense retrieval encodes queries and documents as dense vectors (embeddings) in a continuous high-dimensional space. Documents are retrieved based on vector similarity, capturing semantic meaning beyond keyword matching.

## Dense vs Sparse Retrieval

### Dense Retrieval
- **Representation**: Continuous vectors (e.g., 768 dimensions)
- **Method**: Neural networks create embeddings
- **Similarity**: Cosine similarity, dot product
- **Advantages**: Semantic understanding, synonyms
- **Example**: BERT embeddings, Sentence Transformers

### Sparse Retrieval
- **Representation**: High-dimensional sparse vectors
- **Method**: Term frequency based (BM25, TF-IDF)
- **Similarity**: Exact keyword overlap
- **Advantages**: Interpretable, fast for exact matches
- **Example**: BM25, Elasticsearch standard search

## Dense Passage Retrieval (DPR)

Seminal approach from Facebook AI (2020):
- Separate encoders for queries and passages
- BERT-based architecture
- Maximum Inner Product Search (MIPS)
- Significantly outperformed BM25 on open-domain QA

## Modern Dense Retrieval Models

### Bi-Encoders
- Encode queries and documents independently
- Fast retrieval (pre-compute document vectors)
- Examples: Sentence-BERT, DPR, E5, BGE

### Cross-Encoders
- Encode query-document pairs jointly
- Slower but more accurate
- Used for reranking
- Examples: BERT rerankers, Cohere rerank

### Late Interaction
- Multi-vector representations
- Token-level interactions
- Examples: ColBERT, ColPali

## Training Approaches

### Contrastive Learning
- Positive pairs: similar query-document
- Negative pairs: dissimilar items
- Maximize similarity for positives
- Minimize for negatives

### Hard Negative Mining
- Select challenging negative examples
- Improves discriminative ability
- Common in modern embedding models

### Multi-Task Training
- Train on diverse retrieval tasks
- Better generalization
- Examples: E5, GTE models

## Applications

- **Open-Domain QA**: Retrieve passages to answer questions
- **RAG Systems**: Provide context to LLMs
- **Semantic Search**: Find conceptually similar documents
- **Recommendation**: Similar items or content
- **Entity Linking**: Match mentions to knowledge bases

## Implementation

### Libraries
- Sentence Transformers
- Haystack
- Transformers (Hugging Face)
- LangChain, LlamaIndex

### Vector Databases
- Pinecone, Weaviate, Qdrant
- Milvus, Elasticsearch
- pgvector (PostgreSQL)

## Hybrid Dense+Sparse

Best practice combines both:
- Dense for semantic similarity
- Sparse for exact keyword matching
- Fusion with RRF or learned weights
- Superior to either alone

## Advantages

- Semantic understanding
- Cross-lingual capability
- Handles paraphrasing
- Better for natural language queries
- Continuous improvements from new models

## Challenges

- Requires quality training data
- Computational cost for embeddings
- Black-box nature (less interpretable)
- May miss exact term matches
- Domain adaptation can be needed

## Pricing

Varies by embedding model and vector database platform.