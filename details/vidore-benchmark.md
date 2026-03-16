## Overview

ViDoRe (Visual Document Retrieval) is a comprehensive benchmark designed to evaluate the performance of embedding models and retrieval systems on visually rich documents, going beyond traditional text-only retrieval benchmarks.

## Purpose

ViDoRe addresses the need to evaluate retrieval systems on real-world documents that contain:
- Tables and structured data
- Charts and graphs
- Diagrams and illustrations
- Multi-column layouts
- Mixed text and visual content
- Complex document structures

## Benchmark Versions

### ViDoRe V3 (Latest - 2026)
- Most comprehensive version
- Expanded document types
- Enhanced evaluation metrics
- Broader coverage of visual document scenarios

### Earlier Versions
- ViDoRe V2: Intermediate release
- ViDoRe V1: Initial benchmark

## Dataset Characteristics

### Document Types
- Scientific papers with figures and tables
- Technical documentation
- Presentation slides
- Financial reports
- Forms and structured documents
- Multi-page documents with varied layouts

### Evaluation Tasks
- Document retrieval from queries
- Table retrieval
- Figure/chart retrieval
- Mixed content retrieval
- Cross-modal matching

## Evaluation Metrics

### Primary Metrics
- **NDCG@10**: Normalized Discounted Cumulative Gain at rank 10
- **Recall@K**: Recall at various cutoff values
- **MRR**: Mean Reciprocal Rank

### Reporting
- Average NDCG@10 across all tasks
- Per-task breakdowns
- Statistical significance testing

## Leaderboard

### Current Top Performers (February 2026)

**ViDoRe V3 Leaderboard**:
1. **Nemotron ColEmbed V2 (8B)**: 63.42 avg NDCG@10
2. Other ColBERT-style models
3. Multi-modal embedding models
4. ColPali and variants

### Model Categories
- Late interaction models (ColBERT-style)
- Multi-modal embeddings
- Vision-language models
- Dense embeddings with visual support

## Why ViDoRe Matters

### Real-World Relevance
Most real-world documents are visually rich:
- Business documents contain charts and tables
- Academic papers include figures and equations
- Technical docs have diagrams and screenshots
- Reports combine text, visuals, and structured data

### Model Selection
ViDoRe helps practitioners:
- Choose appropriate models for visual documents
- Understand trade-offs between approaches
- Evaluate whether visual understanding is needed
- Compare multi-modal vs text-only retrieval

### Research Direction
Guides research in:
- Multi-modal document understanding
- Visual layout comprehension
- Efficient visual-text retrieval
- Document AI systems

## Use Cases

ViDoRe is relevant for applications involving:
- Scientific literature search
- Enterprise document management
- Technical documentation systems
- Financial document analysis
- Legal document discovery
- Medical record retrieval
- Research paper databases

## Model Types Evaluated

### Late Interaction Models
- ColBERT variants
- ColPali
- ColQwen
- Nemotron ColEmbed

### Dense Embeddings
- CLIP-based models
- Multi-modal transformers
- Vision-language models

### Hybrid Approaches
- Text + visual feature fusion
- Two-tower architectures
- Cross-modal attention models

## Evaluation Process

### Dataset Splits
- Training set (if applicable)
- Validation set
- Test set (held-out)

### Standardized Protocol
- Consistent preprocessing
- Fixed evaluation metrics
- Reproducible results
- Fair comparison framework

## Key Insights from ViDoRe

### Late Interaction Benefits
Late interaction models (ColBERT-style) excel on ViDoRe, suggesting token-level matching is beneficial for complex visual documents.

### Visual Understanding Importance
Models with explicit visual understanding significantly outperform text-only models on documents with complex layouts.

### Scale Matters
Larger models (e.g., 8B parameters) achieve better performance on visual document tasks.

### Layout Awareness
Models that understand document layout and structure perform better than those treating documents as flat text.

## Comparison with Other Benchmarks

### vs MTEB (Massive Text Embedding Benchmark)
- ViDoRe: Visual documents, multi-modal
- MTEB: Text-only evaluation
- Complementary benchmarks

### vs BEIR
- ViDoRe: Visual richness focus
- BEIR: Diverse text retrieval tasks
- Different evaluation goals

### vs MS MARCO
- ViDoRe: Document-level, visual content
- MS MARCO: Passage-level, text passages
- Different granularities

## Technical Details

### Document Processing
- OCR for scanned documents
- Layout analysis
- Visual feature extraction
- Multi-modal fusion

### Query Types
- Natural language queries
- Visual queries (when applicable)
- Structured queries
- Mixed query types

## Best Practices for ViDoRe Evaluation

1. **Consistent Preprocessing**: Use standardized document processing
2. **Fair Comparison**: Follow official evaluation protocol
3. **Multiple Metrics**: Report all standard metrics
4. **Statistical Testing**: Include significance tests
5. **Ablation Studies**: Analyze component contributions

## Limitations

- Focus on English documents primarily
- Limited document type coverage
- Benchmark size constraints
- Domain-specific performance may vary
- Annotation challenges for visual content

## Future Directions

### Planned Enhancements
- Expanded language coverage
- More document types
- Dynamic document updates
- Cross-lingual evaluation
- Multi-modal query support

### Research Opportunities
- Efficient visual document retrieval
- Zero-shot visual understanding
- Domain adaptation studies
- Compression techniques evaluation

## Impact on the Field

ViDoRe has influenced:
- Development of visual document models
- Research in multi-modal retrieval
- Production system design choices
- Benchmark design for document AI
- Industry adoption of visual-aware retrieval

## Access and Participation

### Public Access
- Benchmark datasets available
- Evaluation scripts provided
- Leaderboard submissions accepted
- Documentation and guidelines

### Submission Process
- Follow official evaluation protocol
- Submit predictions for test set
- Include technical report
- Reproducibility requirements

## Resources

- Official website with leaderboard
- GitHub repository with code
- Paper describing benchmark
- Community discussions
- Tutorial materials

## Significance

ViDoRe represents a crucial step toward more realistic evaluation of document retrieval systems, acknowledging that real-world documents are inherently multi-modal and visually rich, not just plain text.