## Overview

Promptfoo is a CLI and library for evaluating and red-teaming LLM applications. As of March 16, 2026, Promptfoo joined OpenAI while remaining open-source under the MIT license.

## Key Features

- **Comprehensive Testing**: Test prompts, agents, and RAGs with automated vulnerability scanning
- **Provider Comparison**: Compare outputs across 50+ LLM providers including GPT, Claude, Gemini, and Llama
- **Red Teaming**: Systematic adversarial testing to detect content policy violations, information leakage, and API misuse
- **CI/CD Integration**: Automatically evaluate prompts and test for security vulnerabilities before deployment
- **Developer Friendly**: Fast with live reloads and caching
- **Language Agnostic**: Define test cases without writing code

## Philosophy

The goal: test-driven LLM development, not trial-and-error. Simple, declarative test cases enable automation without heavy notebooks or extensive coding.

## Assertions and Validation

Use assertions to compare LLM output against expected values or conditions. Validate output through:
- Equality checks
- JSON structure validation
- Similarity scoring
- Custom functions

## Use Cases

- Automated prompt regression testing
- Security scanning for production deployments
- Comparing LLM provider performance
- RAG application evaluation
- Agent behavior validation

## Pricing

Free and open-source under MIT license.