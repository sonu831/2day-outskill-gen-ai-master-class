# 02 — App Architecture

Every app has the same three layers. Knowing them lets you tell the AI what to
build and where each piece lives.

## The three layers

| Layer | What it is | Example |
|-------|-----------|---------|
| **Front-end** | The UI — what you see and tap | Buttons, forms, pages |
| **Back-end** | The logic/processing behind the scenes | "save this order", "compute total" |
| **Database** | The app's memory, stored in tables | users, orders, products |

```
Front-end  ⇄  Back-end  ⇄  Database
  (UI)         (logic)       (memory)
```

## Front-end

- What the user sees and interacts with.
- Sends requests to the back-end; displays the results.
- Vibe-coding tip: describe screens and interactions; the AI builds the UI.

## Back-end

- The logic and processing behind the scenes.
- Receives requests from the front-end, applies rules, reads/writes the
  database, returns results.
- Vibe-coding tip: describe the *rules* ("a user can't order out-of-stock
  items") and the AI implements the handlers.

## Database

- The app's **memory**, stored in **tables** (rows and columns).
- Persistent — survives restarts. Everything the app must remember lives here.
- Vibe-coding tip: describe the entities ("users have many orders") and the AI
  designs the schema.

## Why the split matters for vibe coding

When you can name the layer, your prompts get precise: "add a *back-end* route
that writes a new order to the *database*, and a *front-end* button that calls
it." Precision → fewer wrong turns.

## Recap

- Every app = **front-end** (UI) + **back-end** (logic) + **database** (memory).
- Name the layer in your prompts to build precisely.
- AI handles the typing across all three; you direct.

---

**Next:** [03 — APIs](./03-apis.md)
