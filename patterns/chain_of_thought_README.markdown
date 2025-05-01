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
The odd numbers in this group add up to an even number: 4, 8, 9, 15, 12, 2, 1.
A: Adding all the odd numbers (9, 15, 1) gives 25. The answer is False.
The odd numbers in this group add up to an even number: 17,  10, 19, 4, 8, 12, 24.
A: Adding all the odd numbers (17, 19) gives 36. The answer is True.
The odd numbers in this group add up to an even number: 16,  11, 14, 4, 8, 13, 24.
A: Adding all the odd numbers (11, 13) gives 24. The answer is True.
The odd numbers in this group add up to an even number: 17,  9, 10, 12, 13, 4, 2.
A: Adding all the odd numbers (17, 9, 13) gives 39. The answer is False.
The odd numbers in this group add up to an even number: 15, 32, 5, 13, 82, 7, 1. 
A:
```

**Output**:
```
Adding all the odd numbers (15, 5, 13, 7, 1) gives 41. The answer is False.
```

## Best Practices

- Use clear instructions like "Think step by step" or "Show your reasoning."
- For few-shot CoT, provide examples with detailed intermediate steps.
- Ensure the problem is well-defined to avoid ambiguous reasoning paths.

## References

- Wei, J., et al. (2022). Chain of Thought Prompting Elicits Reasoning in Large Language Models. *arXiv preprint arXiv:2201.11903*.
