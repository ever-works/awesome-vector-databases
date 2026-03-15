## Overview

Self-Querying Retriever uses an LLM to decompose natural language queries into two components: a semantic search query and structured metadata filters. This enables more precise retrieval than vector search alone.

## The Problem

User: "Find recent articles about Python written after 2023"

Standard vector search:
- Embeds entire query
- Can't separate semantic intent from filters
- May retrieve old articles or non-Python content

## How Self-Querying Works

### Query Decomposition
LLM breaks query into:
1. **Semantic query**: "articles about Python"
2. **Metadata filters**: `{"year": {"$gt": 2023}, "language": "Python"}`

### Execution
```python
results = vectorstore.search(
    query="articles about Python",  # Semantic
    filter={"year": {"$gt": 2023}}  # Structured
)
```

## Implementation

```python
from langchain.retrievers.self_query.base import SelfQueryRetriever
from langchain.chains.query_constructor.base import AttributeInfo

# Define metadata schema
metadata_field_info = [
    AttributeInfo(
        name="year",
        description="The year the document was published",
        type="integer",
    ),
    AttributeInfo(
        name="language",
        description="Programming language",
        type="string",
    ),
]

retriever = SelfQueryRetriever.from_llm(
    llm=llm,
    vectorstore=vectorstore,
    document_contents="Articles about programming",
    metadata_field_info=metadata_field_info,
)

docs = retriever.get_relevant_documents(
    "Recent Python articles from 2024"
)
```

## Benefits

- **Precision**: Filters irrelevant results
- **Natural Language**: Users don't need to know filter syntax
- **Efficiency**: Pre-filters before distance computation
- **Better Results**: Combines semantic + structured search

## Example Queries

"Movies with Tom Hanks from the 1990s"
→ Semantic: "Tom Hanks movies"
→ Filter: `{"year": {"$gte": 1990, "$lt": 2000}}`

"Cheap hotels near the beach"
→ Semantic: "hotels near beach"
→ Filter: `{"price": {"$lt": 100}, "location": "beach"}`

## Requirements

- Vector database with metadata filtering
- LLM for query decomposition
- Well-defined metadata schema
- Properly indexed metadata fields

## Pricing

Adds small LLM API cost per query for decomposition.