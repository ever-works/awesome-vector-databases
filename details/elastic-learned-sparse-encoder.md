## Overview

Elastic Learned Sparse Encoder (ELSER) is a learned sparse encoding model developed by Elastic that brings semantic search capabilities to Elasticsearch while maintaining the efficiency and explainability of traditional keyword search.

## Key Innovation

ELSER combines the best of both worlds:
- **Semantic Understanding**: Neural network-based semantic comprehension
- **Sparse Representation**: Efficient sparse vectors for fast retrieval
- **Term Expansion**: Automatic expansion with related terms
- **Native Integration**: Built directly into Elasticsearch

## How It Works

### Architecture

ELSER uses a learned sparse encoding approach:

1. **Term Expansion**: Expands queries and documents with semantically related terms
2. **Sparse Vectors**: Generates sparse vector representations
3. **Efficient Storage**: Leverages Elasticsearch's inverted index
4. **Fast Retrieval**: Uses BM25-like retrieval with semantic enhancement

### Advantages of Sparse Encoding

- Storage efficient compared to dense vectors
- Faster retrieval than approximate nearest neighbor search
- Explainable results (can see which terms matched)
- No need for separate vector database infrastructure

## Performance

ELSER achieves strong retrieval performance:
- Semantic understanding comparable to dense embeddings
- Faster query execution than dense vector search
- Lower storage requirements than dense vectors
- Better zero-shot performance on domain-specific queries

## Features

- **Zero-Shot Learning**: Works without domain-specific training
- **Multilingual Support**: Handles multiple languages
- **Explainability**: Clear visibility into why documents matched
- **Hybrid Search**: Can be combined with traditional BM25 search
- **Native Integration**: No external embedding service required
- **Automatic Deployment**: Easy setup within Elasticsearch

## Use Cases

- Enterprise search applications
- Document retrieval systems
- Question answering platforms
- Knowledge base search
- E-commerce product search
- Legal document discovery

## Comparison with Dense Vectors

### ELSER Advantages
- Faster retrieval speed
- Lower storage costs
- Explainable results
- Better integration with existing Elasticsearch features

### Dense Vector Advantages
- Higher semantic precision in some cases
- Better for cross-modal search (image-text)

## Integration

### Elasticsearch Setup

ELSER can be deployed directly in Elasticsearch:

```json
PUT _ml/trained_models/.elser_model_2
{
  "input": {
    "field_names": ["text_field"]
  }
}
```

### Ingestion Pipeline

Automatic inference during document indexing:

```json
PUT _ingest/pipeline/elser-ingest
{
  "processors": [
    {
      "inference": {
        "model_id": ".elser_model_2",
        "input_output": [
          {
            "input_field": "content",
            "output_field": "content_embedding"
          }
        ]
      }
    }
  ]
}
```

### Search Query

```json
GET my-index/_search
{
  "query": {
    "text_expansion": {
      "content_embedding": {
        "model_id": ".elser_model_2",
        "model_text": "How to install security patches?"
      }
    }
  }
}
```

## Model Versions

- **ELSER v1**: Initial release
- **ELSER v2**: Improved performance and accuracy
- Regular updates with enhanced capabilities

## Performance Characteristics

- Query latency: Sub-100ms typical
- Storage: ~100 tokens per document on average
- Recall: Competitive with dense vector approaches
- Throughput: High queries per second

## Best Practices

- Use ELSER for text-heavy enterprise search
- Combine with traditional BM25 for hybrid search
- Monitor resource usage during inference
- Use appropriate field mappings for optimal performance
- Consider document length when planning capacity

## Advantages for Production

- No external embedding service required
- Unified infrastructure (no separate vector database)
- Leverages Elasticsearch scaling and reliability
- Familiar query syntax and operations
- Built-in monitoring and management

## Pricing

Included with Elasticsearch, available on:
- Elastic Cloud (managed service)
- Self-managed Elasticsearch deployments
- Pricing based on Elasticsearch licensing tiers