## Efficient Multi-vector Dense Retrieval with Bit Vectors (emvb)

**Category:** Curated Resource Lists  
**Type:** Open-source research implementation / specialized vector-search index  
**Source:** [GitHub – CosimoRulli/emvb](https://github.com/CosimoRulli/emvb)

emvb is an open-source implementation of the ECIR 2024 method "Efficient Multi-vector Dense Retrieval with Bit Vectors." It provides a specialized index for multi-vector dense retrieval that uses compact bit-vector representations to speed up approximate nearest neighbor (ANN) search and reduce memory usage in vector databases and retrieval systems.

---

### Features

#### Core Capabilities
- Implements the **Efficient Multi-vector Dense Retrieval with Bit Vectors** method from ECIR 2024.
- Specialized **multi-vector dense retrieval** index suitable for ColBERT-style and similar late-interaction models.
- Uses **compact bit-vector representations** to:
  - Accelerate ANN search.
  - Reduce memory consumption compared to standard dense-vector indexes.
- Designed to integrate into **vector database / retrieval system** workflows.

#### Performance & Hardware
- Optimized for CPUs supporting **AVX512** instructions:
  - AVX512 is heavily used for core computations.
  - Code still compiles without AVX512, but retrieval time may increase significantly.
- Uses **Intel MKL** and **Faiss** for underlying numeric and ANN operations.
- Supports single-threaded operation by default; users can parallelize over queries externally (e.g., via `OMP_NUM_THREADS`).

#### Installation & Build
- Requires **Intel Math Kernel Library (MKL)** installed.
  - Must set the `MKLROOT` environment variable to the MKL installation directory.
- Repository must be cloned with submodules: `git clone --recursive`.
- CMake-based build system with Faiss configuration:
  - Example build steps:
    ```bash
    mkdir build && cd build
    cmake -DFAISS_ENABLE_GPU=OFF -DFAISS_ENABLE_PYTHON=OFF ..
    make -j
    ```
- CPU-only build by default (`FAISS_ENABLE_GPU=OFF`).

#### Command-line Parameters (perf_embv)
Running `./build/perf_embv --help` exposes tunable parameters, including:

- Retrieval & scoring:
  - `k`: number of returned results per query.
  - `nprobe`: number of inverted lists (centroid lists) to scan.
  - `thresh`: threshold to filter out non-relevant centroid scores (recommended range `[0.3, 0.6]`; corresponds to _th_ in the paper, see Equation 4 / Figure 2).
  - `thresh-query`: threshold used to define \( \bar{J}_i \) (see Equation 6 in the paper).
  - `out-second-stage`: number of documents passed to the centroid-interaction mechanism after Equation 4.
  - `n-doc-to-score`: number of documents that proceed to the late-interaction scoring phase.

- Paths & I/O:
  - `index-path-dir`: directory containing the inverted index files and compressed collection (pre-built indexes are provided; users can also build their own).
  - `queries-id-file`: path to a `.tsv` file with query IDs.
  - `alldoclens-path`: path to a `.npy` file with document lengths (number of terms per document).
  - `out-file`: path where retrieval results are written.

#### Reproducing Paper Results
- Includes scripts and configuration to reproduce ECIR 2024 results:
  - `results_msmarco.sh` for MS MARCO experiments.
  - `results_lotte.sh` for LOTTE experiments.
- Requires setting `export OMP_NUM_THREADS=1` to avoid implicit multi-threading by Faiss and MKL, which can negatively impact intra-query performance.
- Uses metrics scripts from the original **ColBERT** repository to compute evaluation metrics.
- Pre-built indexes can be downloaded from the provided URL, with filenames formatted as:
  - `{n_centroids}k_{M}_m_{dataset}_{compression_mod}.tar.gz`

#### Extending to New Collections
To apply the index to a custom collection, you must provide:

- `doclens` file: document lengths (terms per document).
- `query_ids` file: query identifiers.
- `index` directory with the following contents:
  - `centroids.npy`: numpy array of centroid representations.
  - `centroid_to_pids.txt`: text file where the *i*-th line lists document IDs assigned to the *i*-th centroid.
  - `index-assignments.npy`: numpy array with, for each vector, the ID of its closest centroid.
  - `pq_centroids.npy`: numpy file with centroids for product quantization (PQ) (used for compressed representations and efficient ANN search).

These components allow building and running the EMVB index on arbitrary multi-vector dense collections.

---

### Requirements
- CPU with **AVX512** support recommended (for full performance).
- **Intel MKL** installed and `MKLROOT` environment variable set.
- C++ toolchain with CMake and support for building Faiss.

---

### Pricing
- **Open-source**: no pricing information; available free of charge under the license specified in the GitHub repository.