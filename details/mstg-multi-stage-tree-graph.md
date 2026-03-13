## Overview

Multi-Stage Tree Graph (MSTG) is a hierarchical vector index developed by MyScale that overcomes limitations of traditional IVF (Inverted File Index) through a hierarchical design.

## Key Innovation

MSTG creates multiple layers unlike IVF which has a single layer of cluster vectors. This hierarchical approach enables:
- More efficient search traversal
- Better handling of complex vector distributions
- Improved recall at comparable latency

## Hierarchical Design

The multi-stage architecture allows for:
- Progressive refinement of search results
- Better balance between accuracy and speed
- More flexible trade-offs between recall and performance

## Advantages Over IVF

### Single Layer vs Multi-Layer

- **IVF**: Single layer of cluster vectors
- **MSTG**: Multiple hierarchical layers for progressive search

### Search Efficiency

The tree-based structure enables faster traversal compared to flat IVF indexes, especially for large-scale datasets.

## Use Cases

- Large-scale vector search
- Applications requiring high recall
- Systems needing balanced performance/accuracy trade-offs
- Enterprise vector databases

## Performance Characteristics

Provides improved performance over traditional IVF while maintaining computational efficiency through intelligent hierarchical organization.

## Pricing

Available as part of MyScale vector database.