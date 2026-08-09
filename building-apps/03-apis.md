# 03 — APIs

An **API** (Application Programming Interface) is a **middleman** with a key
that connects different pieces of software so they can talk to each other.

## The mental model

```
Your app  ⇄  [API: the middleman]  ⇄  Another service
                  (key)
```

- You send a request with an **API key** (your permission / identity).
- The API forwards it to the service (a payment provider, a maps service, an AI
  model…).
- The service returns data; the API hands it back to your app.

## Why APIs matter

- **Connect without rebuilding** — use Stripe for payments, Maps for location,
  Claude for AI, without writing those systems yourself.
- **Keys = access control** — the key identifies you and what you're allowed to
  do.
- **Contracts** — an API defines what you can ask and what you'll get back.

## Two flavors you'll meet

- **REST APIs** — request/response over HTTP (most common). e.g., `GET /orders`.
- **AI model APIs** — send a prompt, get a response. (See
  [Using the Claude API](../claude/02-api-basics.md).)

## Vibe-coding with APIs

- Describe the integration: "use the OpenWeather API to show today's forecast."
- Provide the API key via environment variables — never hard-code it (see
  [Limitations & Risks](../generative-ai/06-limitations-and-risks.md)).
- Treat data from APIs as **untrusted** (prompt injection can ride in via API
  responses).

## Recap

- An API is a keyed middleman connecting software to software.
- Keys grant access; the API contract defines what you can ask.
- Never hard-code keys; treat API data as untrusted.

---

**Next:** [04 — Authentication](./04-authentication.md)
