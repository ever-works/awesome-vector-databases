# Image Retrieval in the Wild

**Type:** Conference tutorial  
**Category:** Curated resource lists / Tutorials  
**Event:** CVPR 2020 Tutorial  
**Format:** Slides + recorded videos (remote, via Zoom)

## Overview

“Image Retrieval in the Wild” is a CVPR 2020 tutorial focused on building large-scale, practical content-based image retrieval systems for real-world applications. It emphasizes:

- Vector-based image search and approximate nearest neighbor (ANN) algorithms
- System design and deployment for billion-scale visual search
- Cross-modality person re-identification (e.g., low-res, infrared, sketch, text-to-image)
- A live implementation demo of an image search engine using a pre-trained deep model

All presentation slides and videos are accessible from the tutorial schedule.

## Features

### Core Topics

- **Content-based image retrieval foundations**  
  - Role of image retrieval in interacting with large visual collections  
  - Limitations of standard benchmarks (e.g., Oxford buildings) for real-world scenarios

- **Approximate Nearest Neighbor (ANN) search**  
  - Review of state-of-the-art ANN algorithms  
  - Billion-scale approximate nearest neighbor search  
  - Practical guidance on selecting ANN algorithms for specific tasks and constraints

- **Large-scale visual search systems**  
  - Case study: Online C2C marketplace app (Mercari)  
  - Handling over one billion listings and ~15M monthly active users  
  - System design for scalability and high availability  
  - Deployment on Kubernetes for production visual search

- **Heterogeneous person re-identification**  
  - Focus on inter-modality discrepancies as the main challenge  
  - Cross-modality scenarios covered:
    - Low-resolution (LR)
    - Infrared (IR)
    - Sketch
    - Text  
  - Organization and overview of available datasets per scenario  
  - Summary and comparison of representative algorithms and approaches

- **Live-coding demo: image search engine from scratch**  
  - Building a web-based image search system in ~100 lines of Python  
  - Using a pre-trained deep model for feature extraction  
  - End-to-end walkthrough from embedding to search interface

### Access & Materials

- Tutorial held remotely (Zoom) as part of CVPR 2020
- Slides and videos linked directly from the schedule:
  - Opening & context
  - Billion-scale ANN search
  - Large-scale visual search in a C2C marketplace
  - Heterogeneous person re-identification survey
  - Live-coding demo of an image search engine

## Schedule (High-Level)

- **Opening & Billion-scale ANN Search** – Yusuke Matsui  
- **Large-scale Visual Search in the Mercari C2C App** – Takuma Yamaguchi  
- **Break**  
- **Heterogeneous Person Re-identification Survey** – Zheng Wang  
- **Live-coding: Image Search Engine from Scratch** – Yusuke Matsui

## Tags

- Tutorials  
- Multimodal  
- Vector search

## Link

- Tutorial page: https://matsui528.github.io/cvpr2020_tutorial_retrieval/