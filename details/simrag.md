## Overview

SimRAG (Self-Improving Retrieval-Augmented Generation) is a research method that enhances question-answering abilities of large language models by integrating external knowledge, specifically addressing challenges in adapting general-purpose RAG systems to specialized fields like science and medicine.

## Key Approach

SimRAG employs self-training to equip LLMs with joint capabilities of question answering and question generation for domain adaptation:

**Stage I**: Fine-tune the LLM on instruction-following, question-answering, and search-related data

**Stage II**: The same LLM generates diverse domain-relevant questions from unlabeled corpora, with filtering to retain high-quality synthetic examples

## Technical Details

- Generates pseudo-labeled tuples by extracting candidate answers from corpus
- Creates questions conditioned on both document and answer
- Uses round-trip consistency filtering for quality control
- Fine-tunes on filtered pseudo-labeled examples

## Performance

Experiments across 11 datasets, two backbone sizes, and three domains demonstrate SimRAG outperforms baselines by 1.2%-8.6%.

## Applications

- Adapting LLMs to scientific domains
- Medical question answering
- Specialized domain RAG systems
- Low-resource domain adaptation

## Publication

Published at NAACL 2025 and available on arXiv (2410.17952). Authored by researchers from Amazon and Emory University.

## Pricing

Research paper - free to access.