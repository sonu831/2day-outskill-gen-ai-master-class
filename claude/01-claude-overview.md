# 01 — Claude Overview

**Claude** is Anthropic's AI assistant — a family of large language models built
with a focus on being helpful, harmless, and honest. This section moves from
general generative-AI concepts to building real things with Claude.

## Model families (tiers, not version numbers)

Claude ships in **tiers**. Specific version names change over time, so always
check the [Anthropic docs](https://docs.anthropic.com) for the current model id.

| Tier | Best for | Trade-off |
|------|----------|-----------|
| **Opus** | Hardest reasoning, complex coding, long agentic tasks | Slower, higher cost |
| **Sonnet** | Balanced everyday work — most people's default | Good speed/quality balance |
| **Haiku** | Fast, lightweight tasks, classification, high-volume | Lower capability |
| **Fable** | Newer, smaller-footprint tier — check docs for its current niche | Newer; availability varies |

Rule of thumb: start with Sonnet, move to Opus when a task needs deeper
reasoning, drop to Haiku for cheap high-volume work.

## Comparing models across providers

Claude is one family among several. Each major provider ships the same *shape* —
a fast/cheap tier, a balanced tier, and a heavy-reasoning tier:

| Provider | Tiers / notable models |
|----------|------------------------|
| **Claude (Anthropic)** | Haiku · Sonnet · Opus · Fable |
| **ChatGPT (OpenAI)** | Soul · Terra · Luna |
| **Gemini (Google)** | Flash · Pro |
| **Grok (xAI)** | Grok |

> Model names change often. Remember the shape, not the exact name.

Two tools to explore and compare without signing up to every provider:

- **[OpenRouter](https://openrouter.ai)** — one API to 480+ models across
  providers; browse by use case (marketing, legal, tech…) to find
  domain-recommended models.
- **[getmulti](https://getmulti.com)** — send one prompt to many models at once
  and compare outputs side by side. Great for picking the best model per task.

Picking the right one is covered in
[05 — Choosing a Model](./05-choosing-a-model.md).

## What Claude can do

- **Text & writing** — drafting, editing, summarizing, translating.
- **Code** — writing, explaining, debugging, refactoring across many languages.
- **Vision** — understands images and diagrams you attach to a message.
- **Long context** — can read large documents (hundreds of thousands of tokens,
  some models up to ~1M) in a single prompt.
- **Tool use** — call functions you define, fetch live data, run code.
- **Extended thinking** — reasons step-by-step before answering on hard problems.
- **Prompt caching** — cache long prompts to cut cost and latency on repeats.

## Where you can use Claude

- **Claude.ai** — consumer web/app chat interface.
- **Claude API** — build Claude into your own apps (covered in the next note).
- **Claude Console / Projects** — grouped workspaces with shared knowledge and
  custom instructions.
- **SDKs** — official Python (`anthropic`) and Node (`@anthropic-ai/sdk`)
  libraries, plus community SDKs.

## Typical use cases

- Coding assistants and code review
- Document Q&A over long PDFs / codebases
- Customer support automation
- Data extraction and structured output (JSON from messy text)
- Agents that plan, call tools, and take actions
- Research summarization and brainstorming

## How Claude is different in practice

- Responds well to **clear, structured instructions** (it likes XML tags for
  structure — see the prompting note).
- Strong at **long-context** tasks and refusing harmful requests.
- Honors a **system prompt** that sets role, rules, and tone.
- Like every LLM, it can **hallucinate** — verify anything consequential
  (see [06 — Limitations & Risks](../generative-ai/06-limitations-and-risks.md)).

## Questions to explore next

- How do I actually call the API? (→ next file)
- What parameters control the output?
- How do I structure prompts that work reliably?
- Which model should I pick for a given job? (→ [05 — Choosing a Model](./05-choosing-a-model.md))

---

**Next:** [02 — Using the Claude API](./02-api-basics.md)
