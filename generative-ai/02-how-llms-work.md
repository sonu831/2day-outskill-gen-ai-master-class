# 02 — How Language Models Work

## The core idea: next-token prediction

A large language model (LLM) is trained on one fundamental task:

> Given a sequence of tokens, predict the most likely **next token**.

That's it. Everything else — answering questions, writing code, translating —
emerges from this one objective when the model is trained on enough data and
made large enough.

```
Input:    "The cat sat on the"
Model →   predicts "mat" (most likely next token)
```

## Tokens, not words

Models don't read whole words. Text is split into **tokens** — sub-word pieces.

- "hello"        → 1 token
- "hamburger"    → maybe 3 tokens: "ham" + "bur" + "ger"
- "ChatGPT"      → maybe 2–3 tokens

A rough rule: **1 token ≈ 4 characters ≈ 0.75 words** in English.
Different models use different tokenizers, so token counts vary.

## The Transformer architecture (high level)

The Transformer (2017) is the engine behind modern LLMs. Key ideas:

1. **Tokens become embeddings.** Each token is mapped to a vector (list of numbers)
   that captures meaning. Similar words have similar vectors.

2. **Attention.** The model looks at *all* tokens at once and decides which ones
   matter for each position. This is the "attention is all you need" idea — it lets
   the model connect a word to another word far away in the text.

3. **Layers.** The model passes the data through many layers (dozens), each refining
   its understanding. Deeper + wider + more data = more capable.

4. **Output probabilities.** At the end, the model outputs a probability for every
   possible next token in its vocabulary, then samples one.

## From probability to text: sampling

The model gives a probability distribution over the next token. How do we pick one?

- **Greedy:** always pick the highest probability. (Boring, repetitive.)
- **Temperature:** a setting that controls randomness.
  - Low temp (0.0–0.3) → focused, deterministic, safe.
  - High temp (0.7–1.0+) → creative, varied, but riskier/wrong.
- **Top-p / nucleus sampling:** pick from the smallest set of tokens whose
  probabilities add up to p (e.g. 0.9). Filters out unlikely junk.

## A generation loop

Generating a paragraph is really a loop:

```
1. Take the prompt.
2. Run the model → get probability for next token.
3. Sample one token (using temperature/top-p).
4. Append it to the text.
5. Repeat until done (stop token or max length).
```

This is why models are slow for long outputs — each token is a separate pass.

## Parameters and scale

A model's "size" is its **parameter count** (the learned weights).

- GPT-2 (2019): ~1.5B parameters
- Early GPT-3 (2020): ~175B
- Modern models: hundreds of billions to trillions

More parameters + more data + more compute generally means better performance —
this "scaling" observation is a big part of why the field advanced so fast.

## What the model does NOT do

- It doesn't "understand" like a human — it recognizes statistical patterns.
- It has no persistent memory between conversations (unless you provide context).
- It can't access the internet or facts on its own (unless given tools).
- It doesn't "know" it's right; it produces plausible-sounding text.

## Recap

- LLMs predict the next token using a Transformer.
- Tokens ≠ words; sampling settings (temperature, top-p) shape output.
- Generation is a token-by-token loop.
- Scale (data + parameters + compute) drives capability.

---

**Next:** [03 — Training & Fine-Tuning](./03-training-and-finetuning.md)
