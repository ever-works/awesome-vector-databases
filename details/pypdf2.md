## Overview

PyPDF2 is a pure Python library for working with PDF documents. It provides functionality for extracting text, reading metadata, merging PDF files, and other document manipulation tasks. It is commonly used in preprocessing pipelines to extract text from PDF documents (such as research papers) before chunking and embedding them for vector database storage.

## Features

- Extract text content from PDF pages
- Read PDF metadata (title, author, subject, etc.)
- Merge and split PDF files
- Extract document information and annotations
- Pure Python implementation with no external dependencies
- Supports reading encrypted PDFs (with password)

## Common Use Cases

- Extracting text from research papers and academic articles for semantic search
- Preprocessing PDF documents before chunking for vector database ingestion
- Building data pipelines that convert PDF content into searchable embeddings
- Metadata extraction from large PDF corpora

## Limitations

- May produce formatting artifacts (extra spaces, split words) when extracting from complex layouts
- Does not handle images or non-text elements
- Works best with text-based PDFs rather than scanned documents (OCR not included)

## Pricing

Free and open-source under the BSD license.