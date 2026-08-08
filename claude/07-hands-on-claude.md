# 07 — Hands-On Claude

Beyond the API, Claude ships practical features that let you get real work done
without writing code. The mastermind demonstrated three: **file uploads** for
data analysis, **Artifacts** for personal mini-tools, and the **Chrome
extension** for pulling data off web pages.

## Data analysis & dashboards (file uploads)

Upload files directly to Claude (CSV, Excel, PDFs, images) and ask it to analyze,
summarize, pivot, or chart them.

- Upload a sales CSV → "build a monthly revenue breakdown by region."
- Upload invoices/PDFs → extract a structured table and totals.
- Upload a spreadsheet → get a cleaned summary and anomalies flagged.

For **interactive dashboards**, pair this with **Artifacts** (below) so Claude
renders charts/controls you can click, not just static text.

> Sensitive files: meeting notes, financials, PII. Mind where data goes — see
> [Limitations & Risks](../generative-ai/06-limitations-and-risks.md). Long
> documents fit Claude's [long context](./04-tools-and-features.md#long-context).

## Claude Artifacts

An **Artifact** is an interactive component Claude renders in a side panel —
HTML, React, SVG, or Mermaid. You describe a tool; Claude builds it; you use it
and tweak it in chat, no deploy needed.

Great for **personal mini-tools**:

- A **tax / GST calculator** (income → slabs → net payable)
- A loan EMI or compound-interest calculator
- A habit tracker or custom quiz
- A formatting/cleaning tool for messy pasted data

Pattern:

```text
Build a [tool] that takes [inputs], does [logic], and shows [output].
Make it interactive. Use [constraints: currency, locale, rules].
```

Example:

> Build a tax calculator for an Indian freelancer: inputs for gross income,
> business expenses, and the applicable slab; show tax, cess, and net income.
> Make it interactive.

→ Claude returns an Artifact you can run right there and adjust ("add a
presumptive-tax toggle").

## Claude Chrome Extension

A browser companion that reads the current page so you can pipe page content
into a prompt or [skill](./06-skills-and-sops.md).

Use cases:

- Extract a **LinkedIn profile** into structured fields (role, company, skills).
- Extract a **job description** into must-have / nice-to-have / keywords.
- Then act on it: match a profile to a JD, draft a tailored cover letter, or
  build a gap analysis.

> Treat page content as **untrusted** — a hostile page can carry prompt
> injection. See [Limitations & Risks](../generative-ai/06-limitations-and-risks.md).

## Combining the three (workflow ideas)

- **Job hunt:** Chrome extension pulls the JD → Artifacts builds a tailored
  "resume checklist + gap analysis" → save the recipe as a
  [skill](./06-skills-and-sops.md).
- **Finance:** upload bank/credit statements → data analysis → Artifacts
  renders a dashboard → ask follow-up questions.
- **Sales:** scrape a prospect's LinkedIn → [Claude Research](../notes/ai-tools.md)
  deepens the profile → draft outreach.

## Recap

- **File uploads** → analyze data and build dashboards.
- **Artifacts** → personal interactive tools (calculators, trackers) with no
  deploy.
- **Chrome extension** → get structured data off web pages into your pipeline.
- Combine them for end-to-end workflows; mind data sensitivity and injection.

---

**Next:** [AI Skill Levels →](../notes/ai-skill-levels.md) · or revisit
[Claude Overview](./01-claude-overview.md)
