## Overview

KRAGEN (Knowledge Retrieval Augmented Generation ENgine) is a tool that combines knowledge graphs, Retrieval Augmented Generation (RAG), and advanced prompting techniques to solve complex problems with natural language, specifically designed for biomedical applications.

## Key Features

- **Knowledge Graph Integration**: Converts knowledge graphs into vector databases using embeddings for searchable retrieval
- **Graph-of-Thoughts (GoT)**: Dynamically breaks down complex problems into smaller subproblems, solves each using relevant knowledge through RAG, then consolidates solutions
- **Interactive Visualization**: Provides graph visualization for users to interact with and evaluate solution quality and logic
- **Hallucination Reduction**: Limits LLM hallucinations by grounding responses in retrieved knowledge graph facts

## Technical Implementation

KRAGEN uses Weaviate, an open-source vector database, to store embedded knowledge graph information and support various embedding models and query methods. The system is deployed using custom Docker containers.

## Workflow

1. Embeds knowledge graph information into vector embeddings
2. Creates searchable vector database from knowledge graph
3. Uses GoT to decompose complex queries into subproblems
4. Retrieves relevant facts for each subproblem via RAG
5. Consolidates subproblem solutions into final answer
6. Provides visualization of reasoning structure

## Use Cases

- Biomedical problem-solving
- Scientific question answering
- Complex reasoning tasks requiring evidence-based answers
- Multi-hop reasoning over knowledge graphs

## Publication

Published in Bioinformatics journal (June 2024, Oxford Academic).

## Pricing

Free and open-source.