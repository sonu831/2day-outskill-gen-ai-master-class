# 06 — Limitations & Risks

Generative AI is powerful but unreliable in specific ways. Knowing the failure
modes helps you build safely.

## Hallucination

Models generate **plausible-sounding but false** text. They don't distinguish
between "I know this" and "this sounds likely."

- They may invent citations, dates, names, APIs, or code.
- Confidence in tone ≠ correctness.
- Mitigations: ask for sources, use RAG with grounded documents, verify outputs,
  tell it to say "I don't know."

## No real reasoning / weak at exact tasks

- Math and logic can fail, especially multi-step.
- Models can do "reasoning-like" text but aren't reliable calculators.
- Mitigations: ask for step-by-step work, use tools (a calculator/code execution).

## Bias

Training data reflects the world — including its stereotypes and gaps.

- Outputs can over-represent some views, languages, and cultures.
- Mitigations: diverse data, evaluation for bias, careful prompting, human review.

## Knowledge cutoff & freshness

- A model only "knows" facts up to its training cutoff.
- It cannot know today's news, prices, or live data without tools.
- Mitigations: RAG, web search tools, passing current data in the prompt.

## Security & misuse

- **Prompt injection:** hidden instructions in retrieved text or user content that
  try to hijack the model. Treat untrusted text as untrusted.
- **Jailbreaks:** attempts to bypass safety. Don't expose dangerous capabilities.
- **Data leakage:** don't put secrets/PII into prompts you don't control — data
  sent to an API may be logged or used (check provider policy).

## Legal & ethical concerns

- **Copyright:** training data and outputs can raise IP questions. Be careful
  with generated code, images, and text resembling protected works.
- **Accountability:** an AI output is still your responsibility when you publish it.
- **Over-reliance:** leaning on AI for decisions without verification.

## Cost, latency, and environment

- Big models cost money per token and add latency.
- Long contexts multiply cost.
- Training/inference has real energy footprint — be intentional about usage.

## Practical checklist for safe use

- [ ] Verify factual claims, especially names, numbers, citations, code.
- [ ] Don't feed secrets or PII into third-party APIs.
- [ ] Treat retrieved/user text as untrusted (prompt injection).
- [ ] Add a human review step for anything consequential.
- [ ] Disclose AI assistance where appropriate.

## Recap

- Hallucination and weak exact-reasoning are the core technical limits.
- Mind bias, freshness, security, and legal/ethical risk.
- Treat the model as a fast, fallible assistant — verify before you trust.

---

**Next section:** [Claude Overview](../claude/01-claude-overview.md)
