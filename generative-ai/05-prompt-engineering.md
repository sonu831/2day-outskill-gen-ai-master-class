# 05 — Prompt Engineering Basics

Prompt engineering is the practice of writing inputs that reliably get good
outputs from a model. It's part craft, part experimentation.

## Core principles

### 1. Be specific and direct
Vague prompts give vague results. State exactly what you want, in what format,
for what audience.

- Weak: "Write about climate change."
- Better: "Write a 200-word summary of climate change for a 12-year-old. Use
  simple words and one analogy. End with one action they can take."

### 2. Give the model a role
Telling the model who to be frames its tone and depth.

> "You are a senior backend engineer reviewing a pull request..."

### 3. Provide structure and format
Ask for a specific output shape: bullet list, JSON, table, code block.
This reduces rambling and makes output usable.

### 4. Show examples (few-shot)
Demonstrate the pattern with 1–3 examples in the prompt. The model copies
the pattern for new inputs.

```
Input: "I loved it"        → Sentiment: positive
Input: "Terrible service"  → Sentiment: negative
Input: "It was okay"       → Sentiment: ?
```

### 5. Think step-by-step
For reasoning tasks, ask the model to show its work.

> "Think step by step before giving the final answer."

This often improves accuracy on math, logic, and multi-step problems.

### 6. Constrain and guard
- Set limits: "maximum 3 sentences", "don't use jargon".
- Tell it what to do if unsure: "If you're not sure, say you don't know."

## Prompt engineering vs context engineering

A useful split from the mastermind:

- **Prompt engineering** — the *instructions*: what the model should do, in what
  format, with what constraints. (Everything in "Core principles" above.)
- **Context engineering** — the *background* the task lives in: who's asking, the
  domain, prior facts, reference docs. Poor context is the #1 cause of bad
  outputs — the model guesses the world when you don't supply it.

### The 5 layers of context

Layer context deliberately, from outermost to innermost:

| Layer | What it gives the model | Example |
|-------|-------------------------|---------|
| **Identity** | Who the model is, and who you are | "You are a tax CPA; I'm a freelancer in India." |
| **World** | Domain rules, facts, reference docs | "GST is 18% for my services; here are my invoices." |
| **Task** | The specific job to do | "Compute my quarterly GST liability." |
| **Examples** | The desired input→output pattern | "Invoice → {tax, rate, amount} …" |
| **Constraints** | Limits and guardrails | "Cite line items; say 'unsure' if data is missing." |

Stack all five and the model rarely guesses wrong on the *shape* of the answer.
The template at the end of this note is built from these layers.

## Patterns that work

| Pattern | When to use |
|---------|-------------|
| **Zero-shot** | Simple tasks where the model already knows the format |
| **Few-shot** | Custom formats or edge cases the model might guess wrong |
| **Chain-of-thought** | Math, logic, multi-step reasoning |
| **Role prompting** | Need a specific perspective/tone |
| **Decomposition** | Break a big task into smaller sub-tasks |

## Common pitfalls

- **Over-prompting:** cramming too many conflicting instructions.
- **Assuming it "knows" your context:** if it's not in the prompt or context
  window, it's not available.
- **Treating it as a search engine:** it can't fetch fresh data without tools.
- **One-shotting complex tasks:** better to split into steps and chain calls.

## A useful template

```
[Role] You are a [expert] who [goal].

[Task] Do X for [input].

[Constraints]
- [constraint 1]
- [constraint 2]

[Format] Return as [format].

[Examples]
... 1–2 worked examples ...
```

## Recap

- Specific > vague. Role, format, examples, and step-by-step reasoning help most.
- Constrain outputs and tell the model how to handle uncertainty.
- For hard tasks, decompose into steps instead of one giant prompt.

---

**Next:** [06 — Limitations & Risks](./06-limitations-and-risks.md)
