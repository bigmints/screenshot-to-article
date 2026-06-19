---
date: 2026-06-19
topic: jetbrains-mellum2
source: screenshot (LinkedIn — Mitko Vasilev post) | verified via web
---

# JetBrains Mellum2: The 12B MoE Coding Model Built by the Makers of Kotlin

**Source:** LinkedIn post by Mitko Vasilev
**Verification status:** All claims confirmed via arxiv paper, Hugging Face, and JetBrains official site.

---

## Verified Claims

| Claim | Status | Source |
|---|---|---|
| Mellum2 exists as 12B A2.5B MoE | ✅ Confirmed | arxiv:2605.31268, HF |
| Trained on ~11T tokens (10.6T) | ✅ Confirmed | arxiv abstract |
| RLVR post-training | ✅ Confirmed | arxiv: "supervised fine-tuning followed by RLVR" |
| JetBrains (creators of Kotlin) built it | ✅ Confirmed | JetBrains /mellum/ page, HF org |
| Apache 2.0 license | ✅ Confirmed | HF tags: `license:apache-2.0` |
| Runs locally (commodity GPUs) | ✅ Confirmed | Paper: "inference efficiency on commodity GPUs" |
| 64 experts, 8 active per token | ✅ Confirmed | arxiv abstract |
| 128K context window | ✅ Confirmed | arxiv abstract |
| Thinking variant with reasoning trace | ✅ Confirmed | arxiv: "Thinking model that emits explicit reasoning trace" |

---

## 🐦 Tweet

> JetBrains dropped **Mellum2** — a 12B MoE coding model.
>
> 🧠 2.5B active params per token
> 📚 10.6T tokens + RLVR
> ⚡ 128K context, GGUF ready
> 📜 Apache 2.0
>
> The company behind Kotlin & IntelliJ built it. Runs on your machine.
>
> Weights: huggingface.co/JetBrains
>
> #JetBrains #Mellum2 #CodingLLM #LocalAI

---

## 💼 LinkedIn Post

**JetBrains Just Built a Coding LLM That Runs on Your Laptop**

The company behind Kotlin, IntelliJ IDEA, and ReSharper has entered the LLM arena — and they came to play.

**Mellum2** is a 12B-parameter Mixture-of-Experts model with 2.5B active parameters per token. It's an open-weight, Apache 2.0-licensed model trained on approximately 10.6 trillion tokens through a three-phase curriculum that progressively shifts from diverse web data toward curated code and mathematical content.

**Why this matters:**

**1. Built by the people who know developer tools**
JetBrains doesn't just build IDEs — they *own* the language ecosystem (Kotlin), the IDE market (IntelliJ, PyCharm, GoLand), and the developer workflow. Their model understands code at a level that reflects decades of tooling expertise.

**2. Architecture designed for real hardware**
Mellum2 uses 64 experts (8 active per token), Grouped-Query Attention with 4 KV heads, Sliding Window Attention, and a Multi-Token Prediction head that doubles as a built-in draft model for speculative decoding. Every design choice was validated with inference efficiency on commodity GPUs as a hard constraint.

**3. Two flavors, both open**
- **Instruct** — answers directly
- **Thinking** — emits an explicit reasoning trace before its final answer

Both variants extend to a 128K context window via YaRN and are available as GGUF quantizations for immediate use with llama.cpp and Ollama.

**4. Competitive with 4B-14B range models**
At the per-token compute cost of a 2.5B dense model, Mellum2 punches well above its weight class across code generation, math, reasoning, tool use, knowledge, and safety benchmarks.

The weights are live on Hugging Face. JetBrains owns the language, the IDE, and now the brain. Build something.

#JetBrains #Mellum2 #CodingLLM #OpenSource #LocalAI #Kotlin

---

## Notes

- The LinkedIn poster (Mitko Vasilev) added the Kotlin/coroutines commentary as color — JetBrains did invent Kotlin, making the vertical integration claim valid as editorial commentary
- "GB10 GPU" refers to NVIDIA's Project DIGITS, not a Mellum2 requirement
- GGUF quantized versions are available on HF for local inference
