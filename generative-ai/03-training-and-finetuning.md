# 03 — Training & Fine-Tuning

## The three stages of building a modern LLM

Building a model like Claude or GPT generally happens in stages.

### 1. Pre-training

- Train on a massive corpus: web pages, books, code, articles.
- Objective: **next-token prediction** (as in the previous file).
- Result: a **base model** that can complete text but isn't yet a good assistant.
- This stage consumes the most compute and data. It's expensive — millions of dollars.

The base model knows a lot about language and facts, but it won't follow
instructions well or refuse harmful requests yet.

### 2. Post-training / alignment

The base model is turned into a usable assistant. Common methods:

- **Supervised Fine-Tuning (SFT):** train on high-quality
  (prompt → good response) examples written by humans.
- **Reinforcement Learning from Human Feedback (RLHF):**
  1. Generate several responses to a prompt.
  2. Humans rank them best→worst.
  3. Train a "reward model" to predict human preference.
  4. Use RL to optimize the LLM to score higher.
- **Constitutional AI (Anthropic's approach):** the model critiques and
  improves its own outputs using a set of written principles ("constitution"),
  reducing the need for human labeling.

This is where the model becomes helpful, honest, and safe-ish.

### 3. Fine-tuning (downstream, by developers)

End users / developers further train a model on their own data:

- Domain adaptation (medical, legal, your product docs).
- Style/voice alignment.
- Typically cheaper than pre-training; small datasets can work.

Note: many use cases no longer need fine-tuning — good prompting + RAG
(retrieval) + tools often gets you further, cheaper.

## Key concepts

- **Base model vs. instruct/chat model:** the chat model you use is the
  pre-trained model *after* alignment.
- **Alignment tax:** making a model safer/helful can slightly reduce raw
  benchmark performance — a deliberate trade-off.
- **Overfitting:** fine-tuning too hard on narrow data can make a model rigid
  and worse on general tasks.
- **Catastrophic forgetting:** training on new data can make a model "forget"
  old knowledge.

## Data matters more than you think

- Quality > quantity. Curated, clean, diverse data beats a bigger pile of junk.
- Duplicated or low-quality data degrade the model.
- Data composition (code %, languages %, science %) shapes what the model is good at.

## Recap

- Pre-training (next-token prediction) → base model.
- Alignment (SFT / RLHF / Constitutional AI) → usable assistant.
- Fine-tuning → specialization by developers; often optional now thanks to RAG + tools.

---

**Next:** [04 — Context, Memory & Limits](./04-context-and-memory.md)
