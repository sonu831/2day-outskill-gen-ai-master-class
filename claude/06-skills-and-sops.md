# 06 — Skills & SOPs

A **skill** is a saved, repeatable set of instructions — an SOP (standard
operating procedure) for an AI. Write the recipe once, invoke it by name, and
get consistent output every time instead of re-crafting the prompt.

## Why skills matter

- **Consistency** — the same task produces the same shape of output every time.
- **Reuse** — teammates or your future self get the good prompt without
  remembering it.
- **Quality** — a polished skill bakes in the context layers (Identity, World,
  Task, Examples, Constraints) so each run starts well-grounded.
- **Speed** — invoke a name instead of typing a 500-word prompt.

Think of a skill as a **function** and your prompt as a **call** to that
function with just the variable parts.

## Anatomy of a skill

A good skill names the job, sets the role, gives the world, shows the pattern,
and lists constraints — then leaves a clear slot for the input.

```text
<skill name="invoice-extractor">
Role: You are an accounts-payable clerk.
World: Invoices may be PDFs, scans, or emails. GST is 18%.
Task: Extract a JSON record from the invoice.
Examples:
  Input: "Invoice #A1, ₹10,000 + GST" → {"id":"A1","base":10000,"gst":1800,"total":11800}
Constraints: Use the exact keys above. If a field is missing, output null. Never guess.
</skill>
```

Usage becomes: `run invoice-extractor on <this invoice>`.

## Built-in Claude skills

Claude ships ready-made skills for common professional outputs, so you don't
write the formatting instructions yourself:

- **DocX** — generate a polished, formatted document (reports, proposals,
  letters) ready to export as a Word-style file.
- **PPTX** — generate a structured slide deck (titles, bullets, speaker notes)
  ready to export as a PowerPoint-style file.

Use these when the *form* matters as much as the *content*: a client-ready
proposal, a board deck, a formatted report. You supply the content and the
target audience; the skill supplies the layout and structure.

> Availability of built-in skills changes over time — check the current Claude
> product surface for the live list.

## Writing your own skill

1. **Name it** for the job (`meeting-notes`, `bug-triage`, `social-caption`).
2. **Set Identity** — who the model is.
3. **Set the World** — domain rules, style guide, reference docs.
4. **Define the Task** — exactly what to produce.
5. **Give 1–3 Examples** — the input→output pattern.
6. **List Constraints** — format, length, tone, "say 'I don't know'" guardrails.
7. **Mark the input slot** — the variable part the caller fills in.
8. **Test on 3 varied inputs** and refine until output is consistent.

## Skills vs. one-off prompts

| | One-off prompt | Skill |
|--|----------------|-------|
| Lifespan | Once | Reused |
| Context | Re-typed each time | Baked in |
| Consistency | Varies | Stable |
| Sharing | Copy-paste | Distribute the file |

## Recap

- A skill is a **saved SOP for AI** — recipe once, reuse forever.
- Layer all five context layers into it.
- Use built-in skills (DocX, PPTX) when you need professional-form output.
- Treat skills like functions: name, inputs, constraints, examples.

## Questions to explore next

- How does my own ability grow as I use AI more? (→ the skill-levels ladder)

---

**Next:** [07 — Hands-On Claude](./07-hands-on-claude.md) · or revisit
[Claude Overview](./01-claude-overview.md)
