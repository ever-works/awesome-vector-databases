## Overview

Cursor-based pagination (also called scroll or continuation tokens) efficiently retrieves large result sets from vector databases by using cursors that mark position, avoiding the performance issues of offset-based pagination.

## The Problem with Offsets

### Offset-Based Pagination
```sql
SELECT * FROM vectors LIMIT 100 OFFSET 10000
```

**Issues**:
- Database must skip 10,000 rows each time
- Gets slower as offset increases
- Inconsistent results if data changes
- O(offset) complexity

## Cursor-Based Solution

### How It Works
1. Request first page
2. Database returns results + cursor (pointer to next position)
3. Use cursor to get next page
4. Repeat until no more results

### Example
```python
# Qdrant
cursor = None
all_points = []

while True:
    result = client.scroll(
        collection_name="my_collection",
        limit=100,
        offset=cursor
    )
    
    all_points.extend(result[0])  # Points
    cursor = result[1]  # Next cursor
    
    if cursor is None:  # No more results
        break
```

## Benefits

- **Constant Performance**: O(1) regardless of position
- **Consistent Results**: Snapshot isolation
- **Efficient**: No redundant work
- **Scalable**: Works with millions of records

## Use Cases

- Exporting entire collections
- Batch processing all vectors
- Data migration
- Full dataset iteration
- Background sync jobs

## Best Practices

1. **Reasonable Page Sizes**: 100-1000 items
2. **Timeout Handling**: Cursors may expire
3. **Progress Tracking**: Log cursor values
4. **Error Recovery**: Store last successful cursor

## Database Support

- **Qdrant**: scroll() with offset parameter
- **Milvus**: query iterator
- **Weaviate**: cursor in GraphQL
- **Pinecone**: pagination tokens
- **Elasticsearch**: scroll API

## Pricing

Not applicable (query pattern/technique).