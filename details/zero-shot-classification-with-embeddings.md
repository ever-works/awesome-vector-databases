## Overview

Zero-shot classification uses embeddings to categorize items without category-specific training examples. Works by computing similarity between item and category descriptions.

## How It Works

1. Embed category descriptions
2. Embed item to classify
3. Find most similar category
4. Return classification

## Example

```python
categories = [
    "product complaint",
    "shipping inquiry",
    "billing question"
]

# Embed categories
cat_embeddings = [model.encode(c) for c in categories]

# Classify new message
message = "Where is my package?"
msg_embedding = model.encode(message)

# Find closest category
similarities = [cosine_similarity(msg_embedding, c) for c in cat_embeddings]
category = categories[np.argmax(similarities)]  # "shipping inquiry"
```

## Advantages

- No training data needed
- Instant deployment
- Easy to add new categories
- Works across domains

## Use Cases

- Customer support routing
- Content moderation
- Document classification
- Intent detection
- Product categorization

## Pricing

Depends on embedding model used.