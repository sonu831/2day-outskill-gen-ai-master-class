# 03 — Prompt Engineering with Claude

Claude rewards **explicit, well-structured** prompts. Vague prompts give vague
results. This note covers the patterns that work reliably with Claude.

## The system prompt

Set role, rules, and tone in the top-level `system` field — not as a message.
Claude treats it as standing instructions across the whole conversation.

```python
client.messages.create(
    model="<model-id>",
    max_tokens=1024,
    system="You are a senior code reviewer. Be concise. "
           "Flag bugs, then suggest fixes. Refuse unsafe code.",
    messages=[{"role": "user", "content": "..."}],
)
```

## Core principles

- **Tell Claude what to do**, not just what not to do. Positive instructions
  beat a list of prohibitions.
- **Be specific about format.** "Return JSON with keys `title` and `summary`"
  beats "summarize this."
- **Give context.** Who is the audience? What's the goal? What constraints
  matter?
- **Assign a role.** "You are a ..." focuses the output.
- **One task per prompt** when possible; split complex jobs into steps.

## Use XML tags for structure

Claude parses XML-style tags well — they separate instructions, context, and
examples cleanly.

```text
<context>
{paste long background here}
</context>

<instructions>
Write a 3-bullet executive summary of the context above.
</instructions>
```

Tags Claude responds to: `<context>`, `<instructions>`, `<example>`,
`<output>`, `<rules>`. Pick names that fit your task.

## Few-shot examples

Show the pattern, especially for structured output.

```text
Classify the sentiment of each review.

<example>Input: "Loved it, fast shipping" → positive</example>
<example>Input: "Never arrived" → negative</example>

<review>{input}</review>
```

## Let Claude think before answering

For multi-step problems, ask for reasoning first — this materially improves
accuracy on math, logic, and analysis.

- Prompt-level: "Think step by step, then give the final answer."
- API-level: enable **extended thinking** so Claude reasons in a dedicated
  thinking block before the final response (see the tools note).

## Control the output format

- **Prefill the assistant turn** to force a start: pass a final
  `{"role":"assistant","content":"{"}` and Claude continues from there — handy
  for strict JSON.
- **State the schema** and ask for valid JSON only.
- **Set `stop_sequences`** to halt at a delimiter.

## A reusable prompt skeleton

```text
<role>You are a {role}.</role>
<task>{one-sentence goal}</task>
<context>{relevant background / data}</context>
<rules>
- {constraint 1}
- {constraint 2}
</rules>
<output_format>{exact shape, e.g. JSON schema}</output_format>
```

## Common pitfalls

- Vague asks → vague answers ("make it better").
- Cramming multiple tasks into one prompt → mixed results.
- Assuming a model "remembers" across requests — it doesn't; pass full
  context each call (or use prompt caching).
- Not specifying format → prose when you wanted JSON.

## Recap

- Use the `system` prompt for standing role/rules.
- Be explicit, structured, and positive.
- XML tags + examples + a stated format = reliable outputs.
- Let Claude reason on hard problems.

## Questions to explore next

- How do I give Claude real tools and live data? (→ next file)
- How do I handle long documents efficiently?

---

**Next:** [04 — Tools & Extended Features](./04-tools-and-features.md)
