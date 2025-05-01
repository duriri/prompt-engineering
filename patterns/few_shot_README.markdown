# Few-Shot Prompting
(![Few-Shot Prompting](https://github.com/duriri/prompt-engineering/blob/main/patterns/Blank%20diagram.png))

## Overview

Few-Shot Prompting involves providing a small number of input-output examples to guide a large language model (LLM) in performing a task. This technique, popularized by Brown et al. (2020), leverages the model's ability to generalize from examples without requiring fine-tuning, making it versatile for tasks like classification, translation, or text generation.

## How It Works

The prompt includes a few labeled examples (input → output) followed by a new input for the model to process. The examples act as a "template" for the desired output format and style.

## Use Cases

- Text classification (e.g., sentiment analysis).
- Language translation or paraphrasing.
- Structured data generation (e.g., JSON, tables).

## Example

**Prompt**:
```
Classify the sentiment of the following reviews as Positive or Negative:

Review: "The movie was thrilling and kept me on edge!" → Positive
Review: "The plot was confusing and poorly executed." → Negative
Review: "I loved the characters and the soundtrack!" → ?

Output: Positive
```

## Best Practices

- Use 2–5 examples for optimal performance, depending on model capabilities.
- Ensure examples are diverse and representative of the task.
- Maintain consistent formatting between examples and the target input.

## References

- Brown, T., et al. (2020). Language Models are Few-Shot Learners. *arXiv preprint arXiv:2005.14165*.
