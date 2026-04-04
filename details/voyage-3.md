## Overview

Voyage 3 is a general-purpose embedding model from Voyage AI that achieves state-of-the-art performance, outperforming OpenAI's text-embedding-3 by an average of 9.74% across multiple domains while using only 1024 dimensions.

## Model Specifications

- Dimensions: 1024
- Context window: 32,000 tokens
- Pricing: $0.06 per million tokens

## Strengths

- Outperforms OpenAI embeddings by 9.74% on average across domains
- 3-4x smaller dimension compared to OpenAI text-embedding-3-large (3072 dims), significantly reducing storage costs
- 32K token context window enables processing of long documents without chunking

## Considerations

- Newer provider with a smaller ecosystem compared to OpenAI
- May require migration effort for teams already invested in OpenAI infrastructure

## Pricing

$0.06 per million tokens via API. Breakeven with self-hosted infrastructure typically occurs at 50-100M tokens/month.