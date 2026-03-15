## Overview

The cold start problem occurs when recommending or searching for items/users with no or minimal interaction history, making collaborative filtering ineffective.

## Problem Scenarios

### New User
- No past interactions
- No preference profile
- Hard to personalize

### New Item
- No ratings/views/purchases
- Unknown quality
- Won't surface in collaborative filtering

### New System
- Fresh database
- No user behavior data

## Solutions with Vector Embeddings

### Content-Based Embeddings
```python
# Embed item descriptions
item_embedding = model.encode(item.description)

# Find similar items
similar = vectordb.search(item_embedding, k=10)
```

- Works immediately
- Based on content, not interactions
- Good for new items

### Hybrid Approach
```python
# Combine collaborative + content
if user.interaction_count < 10:
    # Use content-based for cold users
    recommendations = content_based_search(user.profile)
else:
    # Use collaborative filtering
    recommendations = collaborative_filtering(user.id)
```

### Popularity Fallback
- Show trending items to new users
- Gather initial interactions
- Bootstrap user profile

## Best Practices

1. **Always have embeddings**: Content-based as safety net
2. **Explicit signals**: Ask users preferences upfront
3. **Progressive enhancement**: Transition from content to collaborative
4. **A/B testing**: Validate cold start strategies

## Vector DB Advantages

- Immediate similarity without interactions
- Content understanding through embeddings
- Hybrid search combining both signals
- Smooth degradation from collaborative to content-based

## Pricing

Not applicable (system design challenge).