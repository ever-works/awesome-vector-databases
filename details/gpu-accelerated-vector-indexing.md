## Overview

Demonstrates efficient vector database querying using GPU acceleration on a large-scale Wikipedia dataset (November 2020 plain text from Kaggle).

## Workflow

- **Embedding Generation**: Use `embedding.py` to generate vector embeddings for Wikipedia articles.
- **Clustering**: Apply K-means clustering with `cluster.py` to group embeddings into 128 clusters.
- **Data Conversion**: Convert `.npy` files to `.bin` format using `convert_npy_bin.py` for C++ compatibility.
- **Query Processing**: Use pregenerated embeddings in `queries_data` folder or generate new ones with `test.py --query "Your query"`.
- **Approximate Nearest Neighbor Search**: Compile and run `IVF.cpp` for GPU-accelerated search.

## Configurable Parameters

Passed as arguments to the executable:
- `n_probe`: 1 to 128 (top clusters for fine search)
- `mode`: "Atomic" or "NonAtomic" (CUDA kernel type)
- `sequential_fine_search`: true/false (separate kernels per cluster or combined)
- `use_cuda_coarse`: true/false (GPU/CPU for coarse search)
- `use_cuda_fine`: true/false (GPU/CPU for fine search)
- `threadsperBlock`: Multiple of 32 (threads per block)

## Pre-uploaded Queries

- query1.bin: "What is learning rate in gradient descent?"
- query2.bin: "What is Microbial biogeography?"
- query3.bin: "Give me details about The Arch of Cabanes."
- query4.bin: "Give me details about the history of the Taj Mahal."
- query5.bin: "Tell me something about the labelling used on aid packages created and sent under the Marshall Plan."

## Compilation and Execution

On CUDA-enabled machine (e.g., cuda5.cims.nyu.edu):
```
module load cuda-12.4
nvcc IVF.cpp cosine_similarity.cu -o IVF
./IVF --n_probe=30 --mode=Atomic --sequential_fine_search=false --use_cuda_coarse=true --use_cuda_fine=true --threadsperBlock=128 --print_results=true
```

## Experiment Analysis

Use `run_multiple_configs.sh <config_file> [num_runs]` to run configurations multiple times and compute average CPU/GPU times.

## Pricing

Free and open-source (GitHub repository).