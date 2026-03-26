## Overview

Vectra is a local vector database for Node.js with features similar to Pinecone but built using local files.

## Key Features

### File-Based Architecture
Each Vectra index is a folder on disk, with an index.json file in the folder that contains all the vectors for the index along with any indexed metadata.

### Pinecone-Style Filtering
Includes Pinecone-style filtering using a familiar subset of MongoDB query operators to filter by metadata before similarity ranking.

### Predictable Performance
Full in-memory scans with pre-normalized cosine similarity deliver sub-millisecond to low-millisecond latency for small/medium corpora.

### Cross-Platform Support
Since Vectra is file based, any language binding can be used to read or write a Vectra index, which means you can build a Vectra index using JavaScript and then read it using Python.

## Best Use Cases

Vectra is intended to be used in scenarios where you have a small corpus of mostly static data that you'd like to include in your prompt, such as:
- Infinite few shot examples
- Single document question answering
- Local development and testing
- Embedded applications requiring vector search

## Installation & Availability

Vectra is available as an npm package and is open-source on GitHub.

## Pricing

Free and open-source.