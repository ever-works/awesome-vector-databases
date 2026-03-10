## Overview

Cosine similarity is one of the most widely used similarity metrics, especially in natural language processing, measuring the cosine of the angle between two vectors while ignoring differences in their size or magnitude.

## How It Works

- Measures the angle between two vectors
- Computed by taking the dot product divided by the product of magnitudes
- Not affected by vector size, only direction
- Values range from -1 (exactly opposite) to +1 (exactly same)
- 0 indicates orthogonality (perpendicular vectors)

## When to Use

- Text embeddings and semantic search
- When direction matters more than magnitude
- Natural language processing tasks
- Comparing normalized embeddings
- Semantic similarity assessment

## Best Practices

- Match the metric used to train your embedding model
- Use for models trained with cosine similarity (e.g., all-MiniLM-L6-v2)
- Preferred when relative direction matters
- Common choice for text semantics

## Relationship to Other Metrics

- When vectors are normalized, dot product ≈ cosine similarity
- Related to Euclidean distance mathematically
- Different from Euclidean in handling magnitude

## Implementation

- Widely supported in all major vector databases
- Fast computation especially for normalized vectors
- Standard metric in embedding APIs
- Native support in Pinecone, Weaviate, Qdrant, Milvus

## Performance

Value closer to 1 indicates higher semantic similarity, making it intuitive for ranking and retrieval tasks in production systems.