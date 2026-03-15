## Overview

Text-to-Cypher is the process of converting natural language questions into Cypher query language for Neo4j graph databases. This enables non-technical users to query complex knowledge graphs and is a key component of GraphRAG systems.

## How It Works

### Process Flow
1. **User Question**: "Who are the colleagues of John working on project Alpha?"
2. **Schema Understanding**: LLM learns graph schema (nodes, relationships, properties)
3. **Query Generation**: LLM generates Cypher query:
```cypher
MATCH (p:Person {name: 'John'})-[:WORKS_ON]->(proj:Project {name: 'Alpha'})
MATCH (colleague:Person)-[:WORKS_ON]->(proj)
WHERE colleague <> p
RETURN colleague.name
```
4. **Execution**: Query runs on Neo4j
5. **Result Formatting**: LLM converts results to natural language

## Key Components

### Schema Representation
LLM needs to understand:
- Node types (labels)
- Relationship types
- Property names and types
- Constraints and indexes

### Prompt Engineering
Effective prompts include:
- Graph schema documentation
- Example queries
- Few-shot learning examples
- Error handling instructions

### Query Validation
- Syntax checking
- Semantic validation
- Safety constraints (prevent expensive queries)
- Result size limits

## Advantages

- **Multi-hop Reasoning**: Traverse multiple relationships
- **Structured Queries**: Leverage graph structure
- **Explainable**: Query shows reasoning path
- **Precise**: Can target specific relationship patterns
- **Complex Patterns**: Handle complex graph traversals

## Challenges

### Schema Complexity
- Large schemas overwhelm LLM context
- Need schema summarization
- Dynamic schema changes

### Query Ambiguity
- Natural language can be ambiguous
- Multiple valid interpretations
- Need clarification mechanisms

### Performance
- Generated queries may not be optimized
- Need query optimization hints
- Index awareness

## Implementation in GraphRAG

### Neo4j GraphRAG Python
```python
from neo4j_graphrag.retrievers import Text2CypherRetriever

retriever = Text2CypherRetriever(
    driver=driver,
    llm=llm,
    neo4j_schema=schema
)

result = retriever.search(
    query_text="Find colleagues of John on Alpha project"
)
```

### LangChain Integration
```python
from langchain.chains import GraphCypherQAChain

chain = GraphCypherQAChain.from_llm(
    llm=llm,
    graph=graph,
    verbose=True
)

response = chain.run("Who works with John?")
```

## Best Practices

1. **Schema Documentation**: Provide clear, concise schema descriptions
2. **Few-Shot Examples**: Include example queries in prompt
3. **Validation**: Always validate generated queries
4. **Safety Limits**: Set query complexity limits
5. **Caching**: Cache common query patterns
6. **Fallback**: Have fallback for failed query generation

## Common Patterns

### Path Finding
"How is Person A connected to Person B?"
```cypher
MATCH path = shortestPath((a:Person)-[*]-(b:Person))
WHERE a.name = 'A' AND b.name = 'B'
RETURN path
```

### Neighborhood Queries
"What are the connections of entity X?"
```cypher
MATCH (x:Entity {name: 'X'})-[r]-(neighbor)
RETURN type(r), neighbor
```

### Aggregation
"How many projects does each person work on?"
```cypher
MATCH (p:Person)-[:WORKS_ON]->(proj:Project)
RETURN p.name, count(proj) as project_count
ORDER BY project_count DESC
```

## Hybrid Approach

Combine Text-to-Cypher with vector search:
1. Vector search finds relevant entities
2. Text-to-Cypher explores relationships
3. Combine results for comprehensive answers

## Evaluation

Metrics for Text-to-Cypher:
- Query syntax correctness
- Semantic accuracy (does it answer the question?)
- Execution success rate
- Query performance
- Answer quality

## Tools and Frameworks

- Neo4j GraphRAG Python package
- LangChain GraphCypherQAChain
- LlamaIndex Knowledge Graph Query Engine
- Custom implementations with LLM APIs

## Future Directions

- Better schema understanding
- Query optimization hints
- Multi-step query decomposition
- Self-correction mechanisms
- Learned query patterns

## Pricing

Depends on LLM provider and Neo4j deployment. Neo4j GraphRAG package is free and open-source.