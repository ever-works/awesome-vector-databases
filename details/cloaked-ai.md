## Overview

Cloaked AI is a security solution from IronCore Labs that enables application-layer encryption for vector embeddings, allowing secure storage and querying of AI data in vector databases like Pinecone, Qdrant, and Weaviate.

## Security Threats Addressed

AI applications rely on vector embeddings to power search and recommendations, but these data-rich vectors introduce new security and privacy risks:
- Data reconstruction attacks from embeddings
- Unauthorized access to vectorized data
- Manipulation of AI applications
- Insertion of bias and inappropriate content

## Encryption Solutions

### Application-Layer Encryption (ALE)

The best way to secure embeddings is using application-layer encryption (ALE), which means you encrypt the data before sending it to a vector database or to an index file using something like FAISS.

### Searchable/Queryable Encryption

Searchable encryption (SE), also called queryable encryption, allows users to search encrypted data without decrypting it. This capability is especially useful when:
- Data privacy is a concern
- Using cloud storage
- Operating in shared environments

### Property-Preserving Encryption

Property-preserving vector encryption lets developers query a vector database if and only if they have the right key. Without the key, they can't meaningfully query it.

## Integration

Works with popular vector databases:
- Pinecone
- Qdrant
- Weaviate
- FAISS

## Best Practices

- Encrypt data both in transit and at rest
- Implement strict access control measures
- Monitor who can view, modify, or manage the database
- Use TLS encryption for data in transit

## Pricing

Enterprise pricing through IronCore Labs.