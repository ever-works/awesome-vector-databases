## Overview

Range Search retrieves all vectors within a specified distance/similarity threshold from a query, instead of returning a fixed k-nearest neighbors. Returns variable number of results based on similarity criteria.

## Comparison

### k-NN Search
"Find 10 nearest neighbors" → Always returns 10 results

### Range Search  
"Find all vectors with similarity > 0.8" → Returns 0 to N results

## Use Cases

- Quality thresholding ("only show high-confidence matches")
- Duplicate detection ("find all near-duplicates")
- Anomaly detection ("nothing similar exists")
- Variable-size result sets
- Similarity-based filtering

## Example

```python
# Qdrant
results = client.search(
    collection_name="my_collection",
    query_vector=query_embedding,
    score_threshold=0.8,  # Only results with score > 0.8
)

# May return 0, 5, 100, or any number of results
```

## Benefits

- Quality control (no poor matches)
- Flexible result sizes
- Natural similarity boundary
- Better for strict requirements

## Challenges

- Unpredictable result count
- Need to choose appropriate threshold
- May return zero results
- Less efficient than k-NN for some indexes

## Pricing

Not applicable (query type supported by most vector databases).