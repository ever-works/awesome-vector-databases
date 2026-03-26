## Overview

XTR (ConteXtualized Token Retriever) introduces a novel objective function that encourages the model to retrieve the most important document tokens first, representing a significant improvement over ColBERT's approach to multi-vector retrieval.

## Key Innovation: Token Selection for Ranking

Prior training algorithms mainly focused on the re-ranking stage, under-estimating the importance of the token retrieval stage. XTR addresses this by:
- Allowing ranking of candidates using only retrieved tokens rather than all tokens
- Enabling a newly designed scoring stage that is 2-3 orders of magnitude cheaper than ColBERT
- Completely removing the gathering stage in multi-vector retrieval

## Performance Improvements

### State-of-the-Art Results
On the popular BEIR benchmark, XTR advances the state-of-the-art by 2.8 nDCG@10 without any distillation.

### Efficiency Gains
- Fast refinement algorithm re-ranks candidates 4,000× cheaper compared to ColBERT's refinement stage
- Leverages token retrieval for both training and inference
- Efficiently obtains candidate document scores by applying scoring on retrieved tokens only

## How It Works

XTR is the first work to simplify the scoring stage by leveraging the token retrieval for both training and inference. This contrasts with traditional ColBERT which requires accessing all token vectors during scoring.

Better token retrieval quality allows for more efficient ranking without sacrificing performance, demonstrating that the token retrieval stage deserves more attention in multi-vector retrieval systems.

## Research Impact

XTR demonstrates that focusing on improving the token retrieval stage, rather than just the re-ranking stage, can lead to significant improvements in both efficiency and effectiveness for multi-vector retrieval systems.

## Pricing

Free research paper and methodology.