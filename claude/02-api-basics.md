# 02 — Using the Claude API

Claude's core API is the **Messages API**. You send a list of messages, Claude
responds with a message. This note shows the shape of a request and response so
you can call it from anything.

> Model ids change over time. Replace `<model-id>` with a current id from the
> [Anthropic docs](https://docs.anthropic.com) (e.g. a Sonnet variant for
> general work).

## The request

`POST https://api.anthropic.com/v1/messages`

Required headers:

| Header | Value |
|--------|-------|
| `x-api-key` | Your API key |
| `anthropic-version` | e.g. `2023-06-01` |
| `content-type` | `application/json` |

Required body fields:

| Field | Meaning |
|-------|---------|
| `model` | The model id to use |
| `max_tokens` | Max output tokens to generate (required) |
| `messages` | Array of `{role, content}` turns |

Optional body fields:

| Field | Meaning |
|-------|---------|
| `system` | Top-level system prompt (sets role/rules) |
| `temperature` | `0.0`–`1.0`; higher = more random |
| `top_p` | Nucleus sampling alternative to temperature |
| `stop_sequences` | Strings that stop generation |

## Minimal example (curl)

```bash
curl https://api.anthropic.com/v1/messages \
  -H "x-api-key: $ANTHROPIC_API_KEY" \
  -H "anthropic-version: 2023-06-01" \
  -H "content-type: application/json" \
  -d '{
    "model": "<model-id>",
    "max_tokens": 1024,
    "messages": [
      {"role": "user", "content": "Explain RAG in one sentence."}
    ]
  }'
```

## Using the Python SDK

```python
import anthropic

client = anthropic.Anthropic()  # reads ANTHROPIC_API_KEY from env

response = client.messages.create(
    model="<model-id>",
    max_tokens=1024,
    messages=[{"role": "user", "content": "Explain RAG in one sentence."}],
)

print(response.content[0].text)
```

## The response

```json
{
  "id": "msg_...",
  "type": "message",
  "role": "assistant",
  "content": [
    {"type": "text", "text": "RAG retrieves relevant documents..."}
  ],
  "stop_reason": "end_turn",
  "usage": {"input_tokens": 12, "output_tokens": 18}
}
```

Key things to notice:

- **`content` is an array** — Claude can return multiple blocks (text, tool
  uses, thinking). Index `[0]` for simple text.
- **`stop_reason`** tells you why it stopped: `end_turn`, `max_tokens`,
  `stop_sequence`, or `tool_use`.
- **`usage`** gives token counts — this is what you're billed for.

## Multi-turn conversations

Pass prior turns back in `messages`. Use `user` for the human and `assistant`
for Claude's previous replies — this is how Claude keeps context.

```python
messages = [
    {"role": "user",      "content": "What is 2+2?"},
    {"role": "assistant", "content": "4"},
    {"role": "user",      "content": "And times 10?"},
]
```

## Notes & gotchas

- `max_tokens` is **required** — unlike some APIs, omitting it errors.
- The `system` prompt is a **top-level field**, not a message with role
  "system".
- Keep secrets out of code — load the key from an environment variable.
- Each token in the context (input + output) counts toward cost and limits.

## Questions to explore next

- How do I write prompts that get good results? (→ next file)
- How do I give Claude tools and long documents? (→ tools note)

---

**Next:** [03 — Prompt Engineering with Claude](./03-prompting-claude.md)
