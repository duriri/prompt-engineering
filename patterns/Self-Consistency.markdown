# 🧠 Self-Consistency Prompting

Self-Consistency Prompting is an advanced technique used in prompt engineering to enhance the **accuracy** and **reliability** of outputs from Large Language Models (LLMs). Instead of relying on a single reasoning path, this method generates multiple reasoning chains and selects the final answer through **majority voting**.

---

## ✨ Why Use Self-Consistency?

While LLMs can follow reasoning chains (using Chain-of-Thought prompting), their outputs may still vary due to randomness or slight missteps in logic. By using Self-Consistency, we mitigate this problem:

* ✅ More stable outputs
* ✅ Fewer reasoning errors
* ✅ Higher accuracy, especially on complex problems

---

## 🛠️ How It Works

1. Prompt the model using **Chain of Thought (CoT)** prompting
2. Sample **multiple outputs** (e.g., 5–10 generations) using a non-zero temperature (e.g., `temperature=0.7`)
3. Extract the **final answer** from each chain
4. Return the answer that appears **most frequently** (majority vote)

---

## 📦 Example

### 🔹 Prompt:

```
# Pseudo-code for generating multiple reasoning paths for a question

def self_consistency_reasoning(problem, num_paths=3):
    """
    Generate multiple reasoning paths to solve the given problem and select the most consistent answer.

    Args:
        problem (str): The problem statement to solve.
        num_paths (int): The number of reasoning paths to generate.

    Returns:
        str: The most consistent answer after evaluating all paths.
    """
    prompt_template = """
    Problem: {problem}
    Reasoning path {path_number}:
    Solve this problem step-by-step, explaining the reasoning for each step.
    Answer (True/False): 
    """

    paths = []  # Store all reasoning paths
    answers = []  # Store all answers (True/False)

    # Generate reasoning paths
    for i in range(num_paths):
        chain = prompt_template.format(problem=problem, path_number=i + 1)
        response = llm.generate(chain)  # Assume this generates reasoning for a path
        paths.append(response)

        # Extract the final answer from the reasoning
        final_answer = extract_answer_from_reasoning(response)
        answers.append(final_answer)

    # Select the most consistent answer (e.g., majority vote)
    consistent_answer = max(set(answers), key=answers.count)

    return consistent_answer

# Example usage:
problem = "The sum of the angles of a triangle is always 180 degrees. True or False?"
result = self_consistency_reasoning(problem)

print(f"Most consistent answer: {result}")

```

### 🔹 Sampled Outputs:
```
Reasoning Path 1: 
- A triangle has three angles.
- In Euclidean geometry, the sum of the interior angles of any triangle is always 180 degrees.
- Conclusion: True.

Reasoning Path 2: 
- A triangle has three angles.
- By the geometry of flat surfaces (Euclidean space), the sum of these angles must always be 180 degrees.
- Conclusion: True.

Reasoning Path 3: 
- A triangle has three angles.
- In Euclidean space, the sum of these angles is 180 degrees, as proven by basic geometry principles.
- Conclusion: True.

Most consistent answer: True
```


## ✅ Best Practices

* Use **Chain-of-Thought** style prompts that guide the model through reasoning
* Generate **5 to 10 completions** for each prompt
* Use a **moderate temperature** (e.g., 0.7) to encourage variation in reasoning paths
* Use a **voting mechanism** to select the final answer

---

## 🧪 When to Use

Self-Consistency is particularly effective for:

* 🧶 Math word problems
* 🤩 Logical puzzles
* 🔗 Multi-step reasoning tasks
* 🧠 Symbol manipulation or programming-related generation

---

## 📚 Reference

Wei, J., Wang, X., Schuurmans, D., Bosma, M., Ichter, B., Xia, F., ... & Le, Q. (2022). **Chain of Thought Prompting Elicits Reasoning in Large Language Models**. *arXiv preprint arXiv:2201.11903*.
