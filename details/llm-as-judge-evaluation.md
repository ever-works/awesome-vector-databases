## Overview

LLM-as-judge uses language models to evaluate other model outputs, particularly useful for assessing RAG systems where traditional metrics fall short. Enables automated, scalable evaluation of semantic quality.

## What LLMs Can Judge

### RAG-Specific Metrics

**Faithfulness/Groundedness**
- Does answer align with retrieved context?
- No hallucinations?
- Citations accurate?

**Context Relevance**
- Is retrieved context relevant to query?
- Does it contain necessary information?
- Too much irrelevant content?

**Answer Relevance**
- Does answer address the question?
- Complete and direct?
- Appropriate level of detail?

**Answer Correctness**
- Factually accurate?
- Logically sound?
- Matches ground truth?

### General Quality

**Coherence**
- Logical flow
- Well-structured
- Easy to follow

**Completeness**
- Addresses all aspects
- Sufficient detail
- No missing information

**Conciseness**
- No unnecessary verbosity
- Clear and direct
- Well-edited

## Implementation Approaches

### Binary Classification
```python
def judge_faithfulness(context, answer):
    prompt = f"""Does the following answer accurately reflect 
    the information in the context? Answer Yes or No.
    
    Context: {context}
    Answer: {answer}
    
    Judgment (Yes/No):"""
    
    response = llm.generate(prompt)
    return "yes" in response.lower()
```

### Scoring (1-5 or 1-10)
```python
def judge_answer_quality(question, answer):
    prompt = f"""Rate the quality of this answer on a scale of 1-5:
    1 = Poor, 2 = Below Average, 3 = Average, 4 = Good, 5 = Excellent
    
    Question: {question}
    Answer: {answer}
    
    Rating (1-5):"""
    
    response = llm.generate(prompt)
    return extract_score(response)
```

### Chain-of-Thought Reasoning
```python
def judge_with_reasoning(context, answer):
    prompt = f"""Evaluate if the answer is supported by the context.
    
    Context: {context}
    Answer: {answer}
    
    Think step-by-step:
    1. What facts does the answer claim?
    2. Are these facts in the context?
    3. Are there any contradictions?
    
    Final judgment:"""
    
    return llm.generate(prompt)
```

## Evaluation Frameworks

### RAGAS
Comprehensive RAG evaluation:
```python
from ragas import evaluate
from ragas.metrics import (
    faithfulness,
    answer_relevancy,
    context_precision,
    context_recall
)

result = evaluate(
    dataset=eval_dataset,
    metrics=[faithfulness, answer_relevancy]
)
```

### TruLens
Observability and eval:
```python
from trulens_eval import TruChain, Feedback

# Define feedback functions
f_groundedness = Feedback(
    provider.groundedness_measure_with_cot_reasons
).on_output()

f_answer_relevance = Feedback(
    provider.relevance
).on_input_output()

tru_app = TruChain(
    app=rag_chain,
    feedbacks=[f_groundedness, f_answer_relevance]
)
```

### Custom Implementation
```python
class RAGEvaluator:
    def __init__(self, judge_llm):
        self.llm = judge_llm
    
    def evaluate_faithfulness(self, context, answer):
        # Prompt engineering for faithfulness
        prompt = self._build_faithfulness_prompt(context, answer)
        score = self.llm.generate(prompt)
        return self._parse_score(score)
    
    def evaluate_relevance(self, query, answer):
        prompt = self._build_relevance_prompt(query, answer)
        score = self.llm.generate(prompt)
        return self._parse_score(score)
    
    def comprehensive_eval(self, query, context, answer):
        return {
            "faithfulness": self.evaluate_faithfulness(context, answer),
            "relevance": self.evaluate_relevance(query, answer),
            "completeness": self.evaluate_completeness(query, answer),
            "coherence": self.evaluate_coherence(answer)
        }
```

## Prompt Engineering

### Clear Instructions
```
Good:
"Rate the factual accuracy of the answer based on the context. 
Use a scale of 1-5 where:
1 = Completely inaccurate
2 = Mostly inaccurate
3 = Partially accurate
4 = Mostly accurate
5 = Completely accurate"

Bad:
"How good is this answer?"
```

### Few-Shot Examples
```python
prompt = """Rate answer relevance (1-5). Examples:

Question: "What is Python?"
Answer: "Python is a programming language."
Rating: 5 (directly answers)

Question: "What is Python?"
Answer: "Programming is important."
Rating: 2 (related but doesn't answer)

Now rate:
Question: {question}
Answer: {answer}
Rating:"""
```

## Calibration and Validation

### Agreement with Humans
```python
def measure_agreement(human_labels, llm_labels):
    from sklearn.metrics import cohen_kappa_score
    
    kappa = cohen_kappa_score(human_labels, llm_labels)
    accuracy = (human_labels == llm_labels).mean()
    
    return {
        "kappa": kappa,  # >0.6 = good agreement
        "accuracy": accuracy
    }
```

### Consistency Checks
```python
def check_consistency(evaluator, sample, n_trials=3):
    scores = [evaluator.judge(sample) for _ in range(n_trials)]
    return {
        "mean": np.mean(scores),
        "std": np.std(scores),
        "consistent": np.std(scores) < 0.5
    }
```

## Advantages

- **Scalable**: Automated evaluation
- **Semantic Understanding**: Captures meaning, not just keywords
- **Flexible**: Adapt to any criteria
- **Explainable**: Can provide reasoning
- **Rapid Iteration**: Fast feedback loop

## Limitations

- **Cost**: LLM API calls per evaluation
- **Latency**: Slower than metrics
- **Consistency**: May vary between runs
- **Bias**: Inherits LLM biases
- **Not Ground Truth**: Still approximation

## Best Practices

1. **Validate First**: Compare with human judgments
2. **Clear Rubrics**: Specific evaluation criteria
3. **Use Strong Models**: GPT-4, Claude for judging
4. **Multiple Runs**: Average over several evaluations
5. **Combine with Metrics**: Use both LLM and traditional
6. **Monitor Costs**: Track API usage
7. **Version Prompts**: Track evaluation prompt changes

## Cost Considerations

```
Evaluating 1000 samples:
  Input: 500 tokens/sample × 1000 = 500K tokens
  Output: 50 tokens/sample × 1000 = 50K tokens
  
  GPT-4 cost: ~$15
  GPT-3.5 cost: ~$1
```

## Pricing

Depends on LLM used; typically $0.001-0.10 per evaluation.