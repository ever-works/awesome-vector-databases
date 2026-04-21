## Overview

Datasets similar to those in ann-benchmarks but augmented with filtering capabilities to test complex filtered vector search scenarios.

## Purpose

Evaluates integration of ANN indices (e.g., HNSW) with filtering:
- Post-filtering: Scales poorly, loses results or needs extra candidates.
- Pre-filtering: Requires full-dataset binary masks, linear size growth.
- Accuracy: HNSW graph disconnection when many vectors filtered.

Qdrant addresses via specialized approach without pre/post-filtering.

## Contents

- Synthetic and real-world datasets.
- Various filter types: keywords, geo-spatial.
- Pre-generated requests for reproducible benchmarks.