# 🧠 Prompt Engineering Patterns

Prompt engineering is the art and science of crafting inputs ("prompts") to get desired outputs from large language models (LLMs) like GPT, Claude, or Mistral. The way you ask matters — even small changes in wording can significantly impact the results.

Although prompts can vary across different models and tasks, there are recurring **prompting techniques** that often work well. In this repository, we explore some of the most common and powerful prompt patterns with clear examples.

---

## 🔍 Why Prompt Patterns Matter?

Each task (e.g. summarization, reasoning, code generation) and each model may respond better to different prompting styles. Instead of writing prompts from scratch every time, it's helpful to learn **repeatable patterns** that often produce better results.

---

## 🧰 Prompting Techniques Covered

Here are some of the most important and widely used prompt engineering methods:

### 🧠 Chain of Thought (CoT)
Encourage the model to reason step by step before answering. Great for logic, math, and reasoning problems.

> "Let's think step by step."

---

### 📚 Few-Shot Prompting
Show the model a few examples of input-output pairs before giving it a new one. Useful when fine-tuning is not available.

> Input → Output  
> Input → Output  
> New Input → ?

---

### 🎯 Zero-Shot Prompting
Give the model a task without any examples — just a clear instruction. Surprisingly powerful with modern models.

> "Summarize the following text in one sentence."

---

### 🧑‍🏫 Role Prompting
Assign a role or identity to the model to influence its behavior or tone.

> "You are a professional editor. Fix grammar and tone in the following text."

---

### 🔁 Self-Consistency
Ask the model multiple times and use majority voting or pick the most consistent answer. Useful to reduce randomness in reasoning tasks.

---

## 🙋‍♀️ Author

**Faeze Abdoli Nejad**  
🎓 M.Sc. in AI (specialized in NLP & LLMs)  
📢 [Telegram: @Ml_duriri](https://t.me/Ml_duriri) – *Simplifying AI for Everyone*

---

---

## 📄 License

MIT License
