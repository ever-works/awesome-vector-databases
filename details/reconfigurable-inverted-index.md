# Reconfigurable Inverted Index (Rii)

**Category:** SDKs & Libraries  
**Tags:** ANN, vector-indexing, similarity-search  
**Website:** https://yusukematsui.me/project/rii/

## Overview
Reconfigurable Inverted Index (Rii) is an open-source research library for approximate nearest neighbor (ANN) and similarity search over high-dimensional vectors. It is built on top of the IVFADC framework and is designed to efficiently support searches over both entire databases and arbitrary subsets, while maintaining performance as new items are added.

## Features
- **Approximate Nearest Neighbor Search**
  - Supports fast similarity search over high-dimensional vectors.
  - Performance comparable to state-of-the-art systems such as Faiss (per the referenced experiments).

- **Reconfigurable Inverted Index Structure**
  - Based on the standard IVFADC system.
  - Uses a specially designed data layout where items are stored linearly.

- **Efficient Subset Search**
  - Enables efficient search over arbitrary subsets of the database.
  - Can switch from inverted-index search to a **linear product-quantization (PQ) scan** when the target subset is small, improving efficiency for constrained queries.

- **Dynamic Updates and Reconfiguration**
  - Data structure can be dynamically adjusted after adding many new items.
  - Maintains fast query speed even after large-scale insertions, mitigating typical performance degradation seen in many ANN systems.

- **Research-Backed Design**
  - Algorithm and data structure are described and evaluated in a peer-reviewed ACMMM 2018 paper.
  - Includes extensive experimental comparisons with existing ANN systems.

## Academic Reference
If you use Rii in academic work, you can cite:

```bibtex
@inproceedings{acmmm_matsui_2018,
    author={Yusuke Matsui and Ryota Hinami and Shin'ichi Satoh},
    title={Reconfigurable Inverted Index},
    booktitle={ACM International Conference on Multimedia (ACMMM)},
    pages={1715--1723},
    year={2018}
}
```

## Pricing
Rii is presented as a research project and open-source library; no pricing or commercial plans are specified on the provided content.