## Overview

Guardrails is a Python framework that helps build reliable AI applications by detecting, quantifying, and mitigating specific types of risks through Input/Output Guards. It provides automatic validation of LLM outputs with pre-built measures called validators.

## Key Features

- **Guardrails Hub**: Collection of pre-built validators for specific risk types
- **Input/Output Validation**: Every prompt and response passes through validation layers
- **Streaming Support**: Validates fragments in real-time as LLM returns them
- **Composable Guards**: Combine multiple validators into Input and Output Guards

## Common Validators

- **PII Detection**: Detect personally identifiable information in text
- **Logical Consistency**: Validate logical consistency and detect/correct fallacies
- **Profanity Check**: Ensure content is appropriate
- **Factuality**: Ensure generated content accuracy and reduce brand risk
- **Toxicity**: Detect harmful or offensive language

## How It Works

Guardrails defines an API and specification format for automatic validation:
1. Input validation inspects incoming user prompts immediately
2. LLM generates response
3. Output validation checks response before returning to user
4. Invalid outputs can be corrected or rejected based on configuration

## Use Cases

- Enterprise AI applications requiring compliance
- Customer-facing chatbots needing content safety
- Document generation with quality requirements
- Applications handling sensitive data
- Brand-safe content generation

## Integration

Works with major frameworks including LangChain, LiteLLM, and OpenAI Agents SDK.

## Pricing

Free and open-source on GitHub.