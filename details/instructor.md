## Overview

Instructor is the most popular Python library for extracting structured data from Large Language Models (LLMs), with over 3 million monthly downloads, 11k+ GitHub stars, and 100+ contributors. It patches the OpenAI Python SDK to add a response_model parameter that maps LLM outputs to Pydantic models.

## Features

- **Type-Safe Extraction**: Built on Pydantic for automatic validation, type safety, and IDE support
- **Multi-Provider Support**: Works with OpenAI GPT models, Anthropic Claude, Google Gemini, open source models via Ollama, DeepSeek, and 15+ other providers
- **Automatic Validation**: Ensures LLM outputs conform to your defined schema
- **Retry Logic**: Automatically retries failed extractions with error feedback
- **Streaming Support**: Process responses in real-time as they're generated
- **Zero-Cost Abstraction**: Simple patch over existing SDK without performance overhead

## Installation

```bash
pip install instructor                    # OpenAI by default
pip install "instructor[anthropic]"       # For Claude
pip install "instructor[google-genai]"    # For Gemini
```

## Basic Usage

```python
import instructor
from pydantic import BaseModel

class User(BaseModel):
    name: str
    age: int

client = instructor.from_provider("openai/gpt-4o-mini")
user = client.chat.completions.create(
    response_model=User,
    messages=[{"role": "user", "content": "John is 25 years old"}],
)
print(user)  # User(name='John', age=25)
```

## Use Cases

- Extracting structured information from unstructured text
- Building reliable data pipelines with LLMs
- Creating type-safe API responses from AI models
- Parsing and validating complex nested data structures

## Pricing

Free and open-source under the MIT license.