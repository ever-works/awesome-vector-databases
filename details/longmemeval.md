## Overview

LongMemEval is a comprehensive benchmark designed to evaluate five core long-term memory abilities of chat assistants: information extraction, multi-session reasoning, temporal reasoning, knowledge updates, and abstention. The benchmark consists of 500 manually created questions and was accepted to ICLR 2025.

## Benchmark Characteristics

The benchmark simulates 115,000-token (LongMemEval_S) and up to 1.5 million-token (LongMemEval_M) settings with multi-session, multi-turn interactions and realistic distractors. LongMemEval presents a significant challenge to existing systems, with commercial chat assistants and long-context LLMs showing a 30% accuracy drop on memorizing information across sustained interactions.

## Recent 2026 Performance Breakthroughs

Several organizations have achieved remarkable results on this benchmark in early 2026:

1. **Supermemory (March 2026)**: Supermemory achieved ~99% on LongMemEval_s using their ASMR (Agentic Search and Memory Retrieval) technique, which uses a multi-agent orchestrated pipeline rather than traditional RAG.

2. **Mastra's Observational Memory (February 2026)**: With gpt-5-mini, Observational Memory scored 94.87% — the highest score ever recorded on this benchmark by any system with any model. With GPT-4o, it achieved 84.23%, outperforming the oracle configuration.

3. **Emergence AI (February 2026)**: At a comparable latency, Emergence AI achieved 86% accuracy on LongMemEval, compared to other systems' lower scores, using RAG-like methods.

The benchmark and code are publicly available on GitHub and Hugging Face for researchers to test their memory systems.

## Pricing

Open-source benchmark, free to use.