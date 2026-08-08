# 04 — Tools & Extended Features

The basics get you text in, text out. The real power is letting Claude **use
tools**, **read long documents**, **remember context cheaply**, and **reason
before answering**. This note surveys the features that matter.

## Tool use (function calling)

You define tools; Claude decides when to call them and with what arguments.

### 1. Define tools with a JSON schema

```python
tools = [{
    "name": "get_weather",
    "description": "Get current weather for a city.",
    "input_schema": {
        "type": "object",
        "properties": {
            "city": {"type": "string", "description": "City name"}
        },
        "required": ["city"],
    },
}]
```

![ ](image.png)

### 2. Claude returns a `tool_use` block

`stop_reason` becomes `"tool_use"`, and `content` contains a block like:

```json
{"type": "tool_use", "id": "toolu_...", "name": "get_weather",
 "input": {"city": "Tokyo"}}
```

### 3. You execute and return `tool_result`

Append the assistant turn, then a `user` turn with a `tool_result` block keyed
by the same `tool_use_id`:

```python
messages.append({"role": "assistant", "content": response.content})
messages.append({
    "role": "user",
    "content": [{
        "type": "tool_result",
        "tool_use_id": tool_use_id,
        "content": "18°C, clear",
    }],
})
```

Then call `messages.create` again — Claude uses the result to finish its answer.

> Treat any data returned to the model as **untrusted** (prompt injection). See
> [Limitations & Risks](../generative-ai/06-limitations-and-risks.md).

## Long context

Most Claude models accept **hundreds of thousands of tokens** in a single
prompt, and some variants take up to ~1M. Good for:

- Whole codebases, long PDFs, transcripts.
- Asking questions over many docs at once.

Trade-offs: long context costs more and adds latency. Don't dump everything if
a small targeted snippet works.

## Prompt caching

Cache large, repeated prompts (system prompts, big docs, few-shot examples) so
re-calls are cheaper and faster.

- Add a `cache_control` marker to the content block to cache.
- Cache reads cost far less than a fresh read; cache writes cost a bit more.
- TTL is ~5 minutes by default, extendable to ~1 hour.
- Best when the same context is reused across many requests.

## Extended thinking

For hard reasoning (math, multi-step logic, complex coding), let Claude think
in a dedicated **thinking block** before the final answer.

- Allocate a thinking budget (in tokens).
- Claude shows its reasoning, then produces the response.
- Pairs well with "think step by step" prompting.

### Reasoning models

Some models are tuned to reason explicitly — they spend extra tokens "thinking"
before answering. Think of them as the heavy-reasoning tier used for hard calls:
architecture trade-offs, multi-constraint decisions, deep debugging, research
synthesis. Reach for **Claude Opus with extended thinking** when a wrong answer
is expensive and a right one is worth the extra latency and cost.

**When to use a reasoning model:**

- The answer depends on several constraints or sequential steps.
- A mistake is costly (money, safety, reputation).
- The task resists a single-shot answer and benefits from being worked out.

**When not to:**

- Simple formatting, classification, or high-volume calls → use a fast tier.
- You need minimum latency — thinking adds time and tokens.

## Vision (images)

Send images as content blocks inside a `user` message:

```json
{"role": "user", "content": [
  {"type": "image", "source": {"type": "base64",
   "media_type": "image/png", "data": "<base64>"}},
  {"type": "text", "text": "What's in this chart?"}
]}
```

Good for diagrams, screenshots, scanned documents, UI review.

## Other useful features

- **Streaming** — stream tokens as they're generated (better UX for chat apps).
- **Batch API** — submit many requests async for a discount, completed within
  ~24 hours. Good for non-urgent bulk jobs.
- **Structured output** — combine a strict JSON schema with tool use to force
  valid JSON.
- **Claude Projects** (Console) — group reference docs and custom instructions
  so a workspace has persistent knowledge.

## Putting it together: a simple agent loop

1. Read the user request.
2. Call `messages.create` with tools.
3. If `stop_reason == "tool_use"`, run the requested tools.
4. Feed `tool_result`s back and loop.
5. When `stop_reason == "end_turn"`, you're done.

This loop is the backbone of most Claude-based agents.

## Recap

- Tools let Claude act, not just talk.
- Long context + prompt caching make big-context apps practical.
- Extended thinking improves hard-reasoning accuracy.
- Agents = an `end_turn` / `tool_use` loop you drive.

---

**Next:** [05 — Choosing a Model](./05-choosing-a-model.md) · or revisit
[Generative AI Foundations](../generative-ai/README.md)
