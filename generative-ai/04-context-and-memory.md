# 04 — Context, Memory & Limits

## The context window

A model can only "see" a fixed amount of text at once — its **context window**,
measured in tokens. Everything in that window is processed together.

```
[ ...everything the model can attend to at once... ]  ← context window
```

- If input + output exceeds the window, the oldest text "falls off" and is forgotten.
- Bigger windows let you analyze long documents, but cost more and can dilute focus.

Modern windows range from ~8K tokens (older/smaller) to 200K–1M+ tokens (recent models).
Claude, for example, supports very large context windows.

## Why context isn't memory

- **No persistent memory by default.** A fresh conversation starts blank. The
  model only knows what's in the current context window.
- "Remembering" across chats requires *you* to store and re-supply information
  (a database, files, or a memory tool).

## Giving the model knowledge: three approaches

### 1. Put it in the prompt (in-context)
- Simplest: paste the text you want it to use into the prompt.
- Works for small amounts; limited by the context window.
- No training needed.

### 2. Retrieval-Augmented Generation (RAG)
- Store your documents in a database with **embeddings** (vector search).
- At query time, retrieve the most relevant chunks and put *those* in the prompt.
- Lets a model answer over huge datasets without fine-tuning.
- Most "chat with your docs" apps use RAG.

### 3. Fine-tuning
- Bake knowledge/style into the model weights.
- Better for stable style or domain behavior, not frequently changing facts.

## Embeddings, briefly

An **embedding** is a vector (list of numbers) that captures the meaning of a
piece of text. Texts with similar meaning have vectors that are close together.

- Used for search, recommendations, and RAG retrieval.
- Cheap and fast compared to running a full LLM.

## Practical limits to remember

- **Output length limits:** even with a big context window, models cap how much
  they generate in one go.
- **Lost-in-the-middle:** models sometimes pay less attention to info buried in
  the middle of a huge context. Put key instructions at the start or end.
- **Cost & latency scale** with input/output tokens.
- **Knowledge cutoff:** a model only "knows" what it was trained on up to a date.
  For fresh info, use tools (search) or RAG.

## Recap

- Context window = how much text the model sees at once; it is *not* memory.
- For persistent knowledge, use the prompt, RAG (embeddings + retrieval), or fine-tuning.
- Mind cost, output limits, and where you place key info.

---

**Next:** [05 — Prompt Engineering Basics](./05-prompt-engineering.md)
