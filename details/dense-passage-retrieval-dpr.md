## Overview

Dense Passage Retriever (DPR) is a set of tools and models for open domain Q&A task developed by Facebook AI Research (now Meta AI). The research shows that retrieval can be practically implemented using dense representations alone, where embeddings are learned from a small number of questions and passages.

## Architecture

DPR uses:
- Dense encoder EP(·) which maps any text passage to a d-dimensional real-valued vector
- Different encoder EQ(·) that maps the input question to a d-dimensional vector
- Two independent BERT networks (base, uncased)
- FAISS for efficient inference-time encoding and indexing

## Performance

When evaluated on a wide range of open-domain QA datasets, the dense retriever outperforms a strong Lucene-BM25 system by 9%-19% absolute in terms of top-20 passage retrieval accuracy.

## Retrieval Process

At run-time, DPR applies the question encoder to map the input question to a d-dimensional vector, and retrieves k passages of which vectors are the closest to the question vector using efficient similarity search.

## Resources

- **GitHub Repository**: github.com/facebookresearch/DPR
- **Models**: Pre-trained models available on Hugging Face
- **Paper**: Available on arXiv (2004.04906)

## Pricing

Free and open-source.