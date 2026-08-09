# 01 — Vibe Coding

**Vibe coding** is building apps by *talking to AI* instead of writing code by
hand. You describe what you want in natural language; the AI writes, edits, and
wires the code. You guide, review, and direct.

## Origin

The term comes from a tweet by **Andrej Karpathy** (co-founder of OpenAI). The
idea: as models get good enough, the bottleneck stops being syntax and becomes
*communication* — saying clearly what you want built.

## Prompting is the most powerful "coding language"

When you can describe a feature in plain language and the AI implements it,
**how you prompt becomes the programming.** Clear specs, good context, and a
precise feedback loop beat memorizing frameworks.

- Vague prompt → buggy app.
- Specific, structured prompt → working app.
- Iterative feedback → refined app.

## What changes vs. traditional coding

| Traditional coding | Vibe coding |
|---------------------|-------------|
| You write syntax | You describe intent |
| You debug line-by-line | You review AI output + describe what's wrong |
| Deep knowledge of one stack | One AI across many stacks |
| Slower to start | Fast prototypes |

You still need to *read* code and reason about architecture — the AI doesn't
replace judgment. It replaces the typing.

## How to vibe-code well

1. **Start small** — one feature at a time.
2. **Give context** — the goal, the stack, the constraints (see
   [context engineering](../generative-ai/05-prompt-engineering.md)).
3. **Review every change** — don't blindly accept.
4. **Iterate with feedback** — "that broke X; fix it so Y" beats starting over.
5. **Keep the app's layers clear** (→ next note).

## Recap

- Vibe coding = building by describing, not typing.
- Prompting is the new programming; clarity beats syntax memorization.
- You still review and direct — the AI does the typing.

---

**Next:** [02 — App Architecture](./02-app-architecture.md)
