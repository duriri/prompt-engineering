# Chain of Thought (CoT) Prompting

## Overview

Chain of Thought (CoT) prompting is a technique that encourages large language models (LLMs) to break down complex problems into intermediate steps before providing a final answer. Introduced by Wei et al. (2022), CoT significantly improves performance on tasks requiring logical reasoning, arithmetic, or multi-step decision-making by making the model's thought process explicit.

## How It Works

In CoT prompting, the user includes an instruction like "Let's think step by step" or explicitly provides examples of step-by-step reasoning. This guides the model to generate intermediate steps, reducing errors and improving transparency.

## Use Cases

- Solving mathematical problems (e.g., algebra, word problems).
- Logical reasoning tasks (e.g., puzzles, deductive reasoning).
- Multi-step decision-making (e.g., planning, troubleshooting).

## Example

**Prompt**:
```
Solve the following problem step by step: If a shirt costs $20 after a 20% discount, what was the original price?

Let's think step by step:
1. Let the original price be X.
2. A 20% discount means the sale price is 80% of the original price, so 0.8X = 20.
3. Solve for X: X = 20 / 0.8.
4. Calculate: X = 25.
Therefore, the original price was $25.
```

**Output**:
```
The original price of the shirt was $25.
```

## Best Practices

- Use clear instructions like "Think step by step" or "Show your reasoning."
- For few-shot CoT, provide examples with detailed intermediate steps.
- Ensure the problem is well-defined to avoid ambiguous reasoning paths.

## References

- Wei, J., et al. (2022). Chain of Thought Prompting Elicits Reasoning in Large Language Models. *arXiv preprint arXiv:2201.11903*.