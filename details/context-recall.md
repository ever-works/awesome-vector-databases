## Overview

Context Recall (also known as Context Sufficiency) measures whether the retrieval context contains all the information required to produce the ideal output for a given input, assessing completeness of retrieved information.

## What It Measures

- Completeness of retrieved information
- Coverage of necessary facts
- Sufficiency for answering queries
- Information gaps in retrieval
- Ability to support complete responses

## Why It Matters

- Incomplete context leads to incomplete answers
- Missing information degrades generation quality
- Affects factual accuracy
- Critical for complex queries
- Determines upper bound on answer quality

## Evaluation Approach

- Requires comparison with gold/ideal answer
- Checks if context includes all needed facts
- Identifies missing information
- Measures completeness percentage
- Assesses information sufficiency

## High Context Recall Indicates

- All relevant information retrieved
- Sufficient context for complete answers
- Good coverage of topic
- Effective retrieval strategy
- Appropriate top-k parameter

## Low Context Recall Causes

- Top-k too small
- Poor chunking strategy
- Information spread across documents
- Retrieval model limitations
- Insufficient index coverage

## Improvement Strategies

- Increase top-k retrieval count
- Optimize chunking approach
- Improve embedding model
- Enhance index coverage
- Use hybrid search methods
- Implement query expansion

## Trade-offs

- Higher recall → more context → higher precision needed
- Balance with context window limits
- Consider latency implications
- Optimize for precision-recall balance

## Comparison with Precision

- **Recall**: Did we get everything needed?
- **Precision**: Is what we got relevant?
- Both metrics essential together
- Optimize for F1 score (harmonic mean)

## Implementation

- Part of RAGAS evaluation framework
- Requires ground truth answers
- Automated computation
- Integration with evaluation pipelines

## Use Cases

- Comprehensive RAG evaluation
- Retrieval optimization
- Top-k tuning
- Quality assurance
- Model selection and comparison