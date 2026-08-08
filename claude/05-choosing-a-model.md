# 05 — Choosing a Model

Every provider ships the same shape — a fast/cheap tier, a balanced tier, and a
heavy-reasoning tier. Choosing well is mostly about matching the **tier** to the
**job**, not memorizing names.

## The three knobs

| Knob | Question | Effect |
|------|----------|--------|
| **Capability** | How hard is the reasoning? | Higher = better answers on hard tasks |
| **Speed** | How fast do you need a reply? | Faster tiers feel instant in apps |
| **Cost** | How many calls, at what volume? | Cheap tiers make bulk jobs affordable |

Pick the lowest-capability tier that still does the job acceptably. Scale up only
when output quality demands it.

## Map the tier to the task

- **Fast/cheap tier** (Claude Haiku / Gemini Flash / ChatGPT Luna-class) →
  classification, routing, summarization, high-volume bulk, chat replies.
- **Balanced tier** (Claude Sonnet / Gemini Pro / ChatGPT Terra-class) →
  everyday writing, coding, analysis. The default for most work.
- **Heavy-reasoning tier** (Claude Opus / ChatGPT Soul-class / Grok) →
  multi-step reasoning, complex coding, agentic loops, hard decisions.

## Domain picks (from the mastermind)

Different models shine in different domains. Use a comparison tool to confirm for
your specific task:

| Domain | What to optimize | Where to start |
|--------|------------------|----------------|
| **Marketing** | Tone, creativity, brand voice | Balanced + high-temp; compare 2–3 |
| **Legal** | Precision, citing clauses, low hallucination | Heavy-reasoning + low-temp + RAG |
| **Tech / code** | Correctness, long context | Heavy-reasoning or balanced w/ tools |
| **Customer support** | Speed, safe canned answers | Fast tier + retrieval |
| **Data / extraction** | Structured output reliability | Balanced, force JSON via tool use |

## Compare before you commit

Don't guess — test side by side on your real task.

- **[OpenRouter](https://openrouter.ai)** — 480+ models through one API; filter by
  use case (marketing, legal, tech…) to shortlist candidates.
- **[getmulti](https://getmulti.com)** — one prompt, many models, outputs shown
  together. The fastest way to see which provider wins for your wording.

## A decision checklist

- [ ] Is the reasoning hard, or is it format/volume work? (sets the tier)
- [ ] Do you need fresh data or tools? (rules out pure text models)
- [ ] What's the cost ceiling per 1k calls?
- [ ] Is latency user-facing? (favor fast tiers)
- [ ] Have you compared 2–3 models on a real sample?

## Recap

- Match **tier to task**; start low and scale up only when quality demands it.
- Domain matters — legal ≠ marketing ≠ code.
- Use OpenRouter to shortlist and getmulti to compare before committing.

## Questions to explore next

- How do I package repeatable instructions into a "skill"? (→ next file)
- When should I use extended thinking / a reasoning model?

---

**Next:** [06 — Skills & SOPs](./06-skills-and-sops.md)
