## Overview

PyLate is a library built on top of Sentence Transformers, designed to simplify and optimize fine-tuning, inference, and retrieval with state-of-the-art ColBERT models.

## Key Features

### Training Capabilities
- Easy fine-tuning on both single and multiple GPUs
- Supports Hugging Face Datasets
- Enables triplet / knowledge distillation based training

### FastPLAID Index
- PyLate provides an efficient index with FastPLAID
- 10x storage compression compared to original PLAID
- Sub-200ms latency for queries
- PyLate leverages PLAID, a purpose-built index for fast ColBERT retrieval

### Multi-Vector Retrieval
Unlike traditional bi-encoders that pool all token representations into a single one, ColBERT models retain all token representations and use late interaction (MaxSim) to compute query/document similarity.

## Performance & Applications

PyLate has enabled the development of state-of-the-art models including GTE-ModernColBERT and Reason-ModernColBERT, demonstrating its practical utility for both research and production environments.

### Advanced Capabilities
- Enhanced out-of-domain generalization
- Long-context handling
- Performance in complex retrieval scenarios
- Preserves individual token embeddings for better semantic matching

## Installation

Available on PyPI:
```bash
pip install pylate
```

## Resources

- GitHub: https://github.com/lightonai/pylate
- Documentation: https://lightonai.github.io/pylate/
- Published at CIKM 2025 with accompanying arXiv paper

## License

Released under MIT license.

## Pricing

Free and open-source.