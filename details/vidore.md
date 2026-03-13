## Overview

ViDoRe (Visual Document Retrieval) Benchmarks define a standard suite of datasets and evaluation protocols for vision-centric document and video retrieval, supporting the assessment of retrieval-augmented generation (RAG) systems and embedding models over complex, multimodal, and multilingual corpora.

## Purpose and Evolution

The ViDoRe suite was created to address the shortcomings of prior retrieval benchmarks—namely, their limited coverage of visual document types, saturation on synthetic/extractive queries, and neglect of multilingual and multi-hop scenarios. Evolving through three major releases (V1–V3 for documents; recent video retrieval adaptation).

## Latest Version (V3)

ViDoRe V3 is a multilingual, human-annotated RAG benchmark that evaluates retrieval, final answer generation, and visual grounding on large industry-relevant document corpora.

### Key Features:

- 26,000 pages and 3,099 queries
- Translated into 6 languages
- Built on 12,000 man-hours of human-created and verified annotations
- 10 challenging, real-world datasets spanning diverse industrial domains
- 8 publicly released datasets and 2 kept private

## Coverage

The benchmark focuses on:
- **Modalities**: Text, figures, infographics, tables
- **Domains**: Medical, business, scientific, administrative
- **Languages**: English, French, and others

## Technical Approach

ViDoRe evaluates a novel concept and model architecture based on Vision Language Models (VLMs) to efficiently index documents purely from their visual features, allowing for subsequent fast query matching with late interaction mechanisms.

## Pricing

Free to use - open benchmark.