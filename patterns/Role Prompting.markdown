# Role Prompting

## Overview

Role Prompting involves assigning a specific persona, role, or expertise to a large language model (LLM) to influence its tone, style, or perspective. This technique, discussed in Liu et al. (2021), is effective for tailoring responses to specific audiences or domains, such as technical writing or creative storytelling.

## How It Works

The prompt begins with an instruction like "You are a [role]" (e.g., teacher, editor, scientist), followed by the task. The model adopts the specified role, adjusting its language and approach accordingly.

## Use Cases

- Professional writing (e.g., editing, report generation).
- Creative tasks (e.g., storytelling as a specific character).
- Domain-specific responses (e.g., legal, medical advice).

## Example

**Prompt**:
```
You are a professional editor. Revise the following text for clarity and conciseness:

[Original text]

Output: [Revised text]
```

## Best Practices

- Choose a role that aligns with the task's requirements.
- Combine with other techniques (e.g., Few-Shot) for enhanced precision.
- Avoid overly vague roles (e.g., "expert") to ensure consistent outputs.

## References

- Liu, P., et al. (2021). Pre-train, Prompt, and Predict: A Systematic Survey of Prompting Methods in Natural Language Processing. *arXiv preprint arXiv:2107.13586*.
