## Passing the Baton: High Throughput Distributed Disk-Based Vector Search with BatANN

**Type:** Research paper / Open-source system  
**Category:** Curated resource (vector search, ANN, distributed systems)  
**Source:** arXiv / PVLDB  
**Code & artifacts:** https://github.com/namanhboi/rdma_anns  
**Paper:** https://arxiv.org/pdf/2512.09331

### Overview
BatANN is a distributed, disk-based approximate nearest neighbor (ANN) vector search system. It targets large-scale datasets (hundreds of millions to billions of vectors) that do not fit in memory and maintains the search behavior of a single global graph while scaling throughput across multiple servers.

It is designed for workloads such as retrieval-augmented generation (RAG), search over unstructured text, and image retrieval, where high-throughput, low-latency vector search over disk-resident data is required.

### Features
- **Distributed disk-based ANN search**  
  - Operates on datasets that are too large for a single server’s memory.  
  - Stores vectors and index structures primarily on disk while serving queries at high throughput.

- **Single global search graph**  
  - Maintains the logical simplicity and logarithmic search complexity of a single global ANN graph across multiple machines.  
  - Differs from sharded or fully independent per-node graphs by enabling coherent global search behavior.

- **“Passing the baton” execution model**  
  - When the search process needs to access a neighborhood stored on a different machine, BatANN transfers the **full query state** to that machine.  
  - The query then continues execution locally on the destination server, improving cache and data locality and reducing cross-node random access.

- **High throughput, near-linear scaling**  
  - Demonstrated near-linear throughput scaling with the number of servers.  
  - On 10 servers and 0.95 recall:
    - On 100M-point datasets: achieves approximately **6.21–6.49×** the throughput of a scatter–gather baseline.  
    - On 1B-point datasets: achieves approximately **2.5–5.10×** the throughput of the same baseline.  
  - Maintains **mean query latency below 6 ms** in these experiments.

- **Network protocol and deployment practicality**  
  - Achieves reported performance using **standard TCP**, not requiring specialized networking hardware or RDMA for core operation (though the repo name suggests RDMA variants are also studied).

- **Open-source artifact availability**  
  - Source code, data, and experimental artifacts are publicly available for reproduction and further research.  
  - Suitable as a reference implementation for large-scale disk-based ANN and distributed vector database designs.

- **Applicability to modern workloads**  
  - Targets web-scale vector databases used in:  
    - Retrieval-augmented generation (RAG) for LLMs.  
    - Search engines over unstructured text.  
    - Image and multimodal retrieval systems.  
  - Designed for settings where accuracy is measured via approximate recall (e.g., 0.95 recall) rather than exact nearest neighbor search.

### Use Cases
- Research and prototyping of large-scale distributed vector search systems.  
- Benchmarking and comparison against scatter–gather and other distributed ANN architectures.  
- Reference design for implementing single-global-graph ANN search across a cluster.

### Pricing
Not applicable. This is a research paper with open-source artifacts rather than a commercial product; no pricing or plans are specified.