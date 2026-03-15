## Overview

Sentence Window Retrieval indexes individual sentences but retrieves a window of surrounding sentences. This balances precision (finding exact relevant sentences) with context (providing enough information for the LLM).

## How It Works

1. **Index**: Each sentence separately with metadata about position
2. **Search**: Find most relevant sentences
3. **Expand**: Retrieve N sentences before and after
4. **Return**: Combined window as context

## Configuration

```python
from llama_index import SentenceWindowNodeParser

node_parser = SentenceWindowNodeParser.from_defaults(
    window_size=3,  # 3 sentences before and after
    window_metadata_key="window",
    original_text_metadata_key="original_text",
)
```

## Benefits

- Fine-grained matching (sentence-level precision)
- Flexible context window
- Less redundancy than overlapping chunks
- Natural sentence boundaries

## Use Cases

- Question answering requiring specific facts
- Citation and attribution
- Legal/medical documents
- When precision matters more than broad context

## Pricing

Implementation-dependent (LlamaIndex feature).