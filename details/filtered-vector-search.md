## Overview

Filtered vector search combines semantic similarity with structured metadata filters, enabling precise queries over vector databases.

## Query Example

"Find similar documents":
- Vector: Semantic similarity
- Filters: `category = 'Technology' AND published > '2023-01-01'`

## Approaches

### Pre-Filtering
1. Apply metadata filters first
2. Search within filtered subset
3. **Pros**: Guarantees filter compliance
4. **Cons**: May reduce recall

### Post-Filtering
1. Vector search first
2. Filter results
3. **Pros**: Better recall
4. **Cons**: May return fewer than k results

### Native Filtered Search
1. Integrated filter + vector search
2. Optimized indexes (e.g., HNSW-IF)
3. **Best**: Efficient and accurate

## Use Cases

- **Time-based**: Recent documents only
- **Category**: Specific content types
- **Access Control**: User permissions
- **Geography**: Location-based
- **Price**: Range constraints

## Database Support

- **Qdrant**: Advanced filtering
- **Weaviate**: Filter operators
- **Milvus**: Scalar filtered search
- **Pinecone**: Metadata filtering
- **pgvectorscale**: SQL WHERE clauses

## Filter Types

- Equality (=, !=)
- Ranges (<, >, <=, >=)
- Lists (IN, NOT IN)
- Boolean logic (AND, OR, NOT)
- Text matching (LIKE)

## Performance

Native implementations much faster than post-filtering. Microsoft's Filtered-DiskANN enables efficient large-scale filtered search.

## Pricing

Feature of vector databases, included in platform costs.