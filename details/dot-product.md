## Overview

Dot product (inner product) is a fundamental vector similarity metric that measures both the directional alignment and magnitude of two vectors. It's widely used in machine learning and vector search.

## Formula

Dot Product = A · B = Σ(a[i] * b[i])

## Characteristics

- **Magnitude Aware**: Considers both direction and vector length
- **Efficient**: Computationally cheaper than Euclidean distance
- **LLM-Friendly**: Many LLMs are trained using dot product
- **Normalized Equivalence**: If data is normalized, equals cosine similarity

## When to Use

- When your embedding model was trained with dot product
- For normalized embeddings (equivalent to cosine)
- When magnitude contains meaningful information
- With LLMs like msmarco-bert-base-dot-v5

## Comparison

- **Cosine**: Reports only angle
- **Dot Product**: Reports angle and magnitude
- **Euclidean**: Measures straight-line distance

## LLM Training

Many Large Language Models use dot product for training, such as:
- msmarco-bert-base-dot-v5 on Hugging Face
- Various BERT variants
- Custom-trained embedding models

## Best Practice

Match your distance metric to your model's training metric. For normalized embeddings, dot product and cosine produce identical rankings.

## Vector Database Support

Supported by all major vector databases including Pinecone, Weaviate, Milvus, Qdrant, and Elasticsearch.