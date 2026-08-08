# AI Skill Levels — Where Are You on the Ladder?

The mastermind framed AI fluency as a progression. Each level unlocks a new kind
of leverage — and a new kind of problem you can solve.

## The ladder

| Level | What you do | Tells |
|-------|-------------|-------|
| **1. Basic User** | Chat with AI occasionally for quick help | Treats AI like a search bar; types one-off prompts |
| **2. Prompter** | Crafts deliberate prompts that work | Uses role, examples, format, context layers; gets reliable single-task results |
| **3. Automator** | Wires AI into repeatable workflows | Calls the API, chains tools, saves prompts as skills, removes manual steps |
| **4. Agent Orchestrator** | Designs agents that plan, call tools, and decide | Coordinates multiple models/skills toward a goal; handles tool loops |
| **5. Builder** | Ships AI products and features | Integrates models, writes evals, fine-tunes, puts AI at the core of software |
| **6. AI Generalist** | Fluent across models, tools, and domains | Picks the right approach for any problem; bridges product, engineering, domain |

## What each level looks like

**Basic User** — "Help me write this email." Hops into Claude.ai or ChatGPT,
asks a question, pastes the answer out. Output quality is hit-or-miss.

**Prompter** — Reaches for context engineering: identity, world, task, examples,
constraints (see [Prompt Engineering Basics](../generative-ai/05-prompt-engineering.md)).
Gets consistent, high-quality single-shot outputs. Most knowledge workers should
aim to live here.

**Automator** — Asks "what can I stop doing by hand?" Uses the
[API](../claude/02-api-basics.md), [tools](../claude/04-tools-and-features.md),
and [skills/SOPs](../claude/06-skills-and-sops.md) to turn a 10-step manual job
into a 1-step run. Time saved compounds.

**Agent Orchestrator** — Designs the agent loop: the model plans, calls tools,
reads results, decides next steps (see the agent loop in
[Tools & Extended Features](../claude/04-tools-and-features.md)). Comfortable
with `tool_use` ↔ `tool_result` cycles and knowing when to use a
[reasoning model](../claude/04-tools-and-features.md#reasoning-models).

**Builder** — Turns workflows into products. Writes evals to measure quality,
manages cost/latency, may fine-tune, ships software with AI inside. This is
where AI fluency meets engineering.

**AI Generalist** — Moves freely across providers ([Choosing a Model](../claude/05-choosing-a-model.md)),
picks the right tier and tool per problem, and can frame the whole system
(product + model + data + evals). The "T-shaped" goal: deep in a few areas,
broad across all of them.

## How to move up a level

- **1 → 2:** Stop typing bare questions. Add role, format, examples,
  constraints every time. Save prompts that worked.
- **2 → 3:** Pick one repetitive task and automate it with the API or a no-code
  integration. Save your best prompts as skills.
- **3 → 4:** Give an agent a goal + tools and let it loop. Start small
  (one tool), then add planning and multi-step.
- **4 → 5:** Add evals, cost/latency budgets, error handling, and ship it to
  real users. Measure quality, not just "it works on my inputs."
- **5 → 6:** Learn other providers and domains; practice choosing models per
  task with OpenRouter / getmulti. Connect product, engineering, and the domain.

## A note on the journey

You don't have to reach level 6 — most high-leverage work happens at levels 2–4.
Move up only where the next level actually unlocks value for your problems.

---

**Back to:** [Learning path (README)](../README.md)
