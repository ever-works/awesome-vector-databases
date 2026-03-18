## Why Prompting Matters in RAG

The prompt is the interface between retrieved context and LLM. Poor prompts lead to:
- Hallucinations despite good context
- Ignoring relevant information
- Poor answer quality
- Context confusion

## RAG Prompt Structure

```
[System Instructions]
[Context/Documents]
[User Query]
[Output Format Instructions]
```

## System Instructions

**Purpose**: Set behavior and constraints

**Good Example**:
```
You are a helpful assistant. Answer questions based ONLY on the provided context. If the context doesn't contain enough information, say "I don't have enough information to answer that."
```

**Key Elements**:
- Role definition
- Context usage instructions
- Handling insufficient information
- Tone and style
- Constraints

## Context Formatting

**Option 1: XML Tags**
```xml
<context>
<document id="1" source="file.pdf">
[content]
</document>
<document id="2" source="web.html">
[content]
</document>
</context>
```

**Option 2: Markdown**
```markdown
## Context Documents

### Document 1 (source: file.pdf)
[content]

### Document 2 (source: web.html)
[content]
```

**Option 3: JSON**
```json
{
  "documents": [
    {"id": 1, "source": "file.pdf", "content": "..."},
    {"id": 2, "source": "web.html", "content": "..."}
  ]
}
```

**Best Practice**: XML or Markdown, consistent structure

## Query Formulation

**Direct**:
```
Question: [user query]
```

**With Context**:
```
Based on the above documents, answer: [query]
```

**Explicit**:
```
Using ONLY the information from the provided context, answer the following question. Cite document IDs for your sources.

Question: [query]
```

## Output Formatting

**Structured Answers**:
```
Provide your answer in this format:

Answer: [your response]
Sources: [list document IDs used]
Confidence: [high/medium/low]
```

**Step-by-Step**:
```
Think through this step-by-step:
1. What does the context say about this?
2. How does it answer the question?
3. What can I conclude?
```

## Anti-Hallucination Techniques

**1. Explicit Constraints**
```
IMPORTANT: Only use information from the provided documents. Do not use your general knowledge. If the documents don't contain the answer, say so.
```

**2. Source Attribution**
```
Cite the document ID for each fact you mention.
Example: "The company was founded in 1998 [Doc 3]"
```

**3. Confidence Scoring**
```
Rate your confidence in this answer (high/medium/low) based on the context quality.
```

**4. Pre-Flight Check**
```
Before answering, confirm:
1. Is this information in the provided context?
2. Am I certain about this?
```

## Few-Shot Examples

**Include Examples in System Prompt**:
```
Example 1:
Context: "The meeting is on Tuesday at 2pm."
Question: "When is the meeting?"
Good Answer: "The meeting is on Tuesday at 2pm."

Example 2:
Context: "The meeting is on Tuesday."
Question: "What time is the meeting?"
Good Answer: "The context doesn't specify the time."

Now answer the following...
```

## Chain-of-Thought for RAG

```
Let's approach this systematically:
1. First, identify relevant passages from the context
2. Extract key information from each passage
3. Synthesize the information
4. Formulate the answer
5. Verify against the context
```

## Handling Multiple Documents

**Comparative Questions**:
```
Compare information across all documents. If they conflict, note the disagreement and cite sources.
```

**Synthesizing**:
```
Synthesize information from multiple documents. Provide a cohesive answer that integrates all relevant facts.
```

## Claude-Specific Tips (2026)

**Extended Thinking**:
```
<thinking>
Let me analyze the context...
</thinking>
```

**Document Position**:
- Claude pays more attention to start and end
- Put most relevant docs at the beginning
- Repeat key info if needed

## GPT-4 Specific Tips

**System Message**:
- Strong adherence to system instructions
- JSON mode for structured output
- Function calling for structured retrieval

## Prompt Optimization Process

1. **Start Simple**: Basic instruction
2. **Test**: Run on diverse queries
3. **Identify Issues**: Where does it fail?
4. **Iterate**: Add constraints/examples
5. **Measure**: Track quality metrics
6. **Refine**: Continue improving

## Common Issues & Fixes

**Hallucination**:
→ Add "ONLY use provided context"
→ Require source citations
→ Add confidence scoring

**Ignoring Context**:
→ Emphasize context usage
→ Add examples showing context usage
→ Use XML tags for clarity

**Overly Verbose**:
→ Add "be concise"
→ Specify length limits
→ Show brief examples

**Missing Sources**:
→ Require citation format
→ Add citation examples
→ Make citations mandatory

## Testing Prompts

**Create Test Set**:
- Questions with known answers
- Questions without answers in context
- Ambiguous questions
- Multi-hop questions

**Evaluate**:
- Correctness
- Source citation accuracy
- Handling of "I don't know"
- Conciseness

## Version Control

- Track prompt changes
- A/B test variations
- Monitor performance metrics
- Roll back if needed

## Best Practices Summary

1. Be explicit about context usage
2. Format context consistently
3. Require source citations
4. Include few-shot examples
5. Handle edge cases
6. Test thoroughly
7. Version and track changes
8. Monitor in production
9. Iterate based on feedback
10. Keep it simple when possible