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

```text
Solve the following problem step-by-step:
If you buy 3 books that cost $12 each and get a $6 discount, how much do you pay?

Let's think step by step.
```

### 🔹 Sampled Outputs:

1. 3 × 12 = 36 → 36 − 6 = **30**
2. 12 × 3 = 36 → 36 − 6 = **30**
3. 3 books: 3 × 12 = 36 → total cost = 36 − 6 = **30**
4. 3 × 12 = 36 → discount is 6 → 36 − 6 = **30**
5. 12 − 6 = 6 → 6 × 3 = **18** ❌ (incorrect logic)

### ✅ Final Answer (by majority):

**30**

---

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
