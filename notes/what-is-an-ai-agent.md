# What is an AI Agent?

![What is an AI Agent? — perceive, think, act, achieve](../image-2.png)

An AI agent is a smart helper that **perceives**, **thinks**, and **acts** to
achieve a goal. The core loop: **PERCEIVE → THINK → ACT → ACHIEVE**.

> Source: mastermind slide "What is an AI Agent?"

## The definition

- AI agents are **systems built using LLMs & tools** to perform tasks or
  automate workflows.
- They can be built **without writing code**.
- They can be **autonomous or semi-autonomous**.

## The perceive–think–act loop

| Step | What happens |
|------|--------------|
| **Perceive** | Gather information — read input, call tools, fetch data |
| **Think** | Reason and decide what to do next |
| **Act** | Take action using tools or services |
| **Achieve** | Deliver the result that meets the goal |

## How it works — example

Goal: *"Find a good pizza place near me."*

1. **Goal** — you tell the agent what you want.
2. **Perceive** — it gathers information (your location, nearby options).
3. **Think** — it reasons and decides (filter by rating/distance).
4. **Act** — it takes action using tools/services (search, maps API).
5. **Result** — it gets the results (a candidate place + rating).
6. **Achieve** — it delivers the answer ("Mario's Pizza, 4.6★, 0.3 mi, open now").

## Agents turn goals into results

The loop above is the same pattern behind every agent — from a pizza finder to a
research or sales agent. The framework handles perceive/think/act; you supply
the goal and the tools.

## Where this fits in the repo

- The agent loop **in code** (`tool_use` ↔ `tool_result`):
  [Tools & Extended Features](../claude/04-tools-and-features.md#putting-it-together-a-simple-agent-loop)
- Where agents sit in the stack (Layer 3 — Execution):
  [LLM vs RAG vs AI Agent vs Agentic AI](./llm-rag-agent-agentic.md)
- The bigger agentic picture:
  [Agentic AI: A Complete Framework](./agentic-ai-framework.md)
- Build agents without code using [Skills & SOPs](../claude/06-skills-and-sops.md)

## Recap

- An agent **perceives, thinks, and acts** to turn a goal into a result.
- It's an LLM + tools system; can be no-code; autonomous or semi-autonomous.
- The 6-step example (goal → perceive → think → act → result → achieve) is the
  universal agent pattern.

---

**See also:** [Hands-On Claude](../claude/07-hands-on-claude.md) ·
[Back to README](../README.md)
