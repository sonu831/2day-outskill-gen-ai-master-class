# 04 — Authentication

**Authentication** answers "who are you?" — it controls **who can access the
app**. (Authorization is the companion: what you're allowed to do once you're
in.)

## The simplest mental model

- **Sign-in** — prove identity (email + password, or Google / GitHub sign-in).
- **Session** — the app remembers you're signed in.
- **Permissions** — what you can see and edit.

## "Sign in with Google" (and friends)

OAuth-based social sign-in lets users log in with an account they already have
(Google, GitHub, Apple). Benefits:

- No password for you to store or lose.
- Less friction → more signups.
- The provider handles security; you focus on your app.

## Supabase

**Supabase** is the tool the mastermind highlighted for auth (and a back-end +
database in one). It gives you:

- Auth out of the box — email, social sign-in, magic links.
- A Postgres database (the [app's memory](./02-app-architecture.md)).
- Auto-generated APIs on top of your data.

So one tool covers the back-end, database, and auth layers — handy for fast
vibe-coded apps.

## Vibe-coding auth

- Describe the access rules: "only the owner can edit their own posts."
- Let the AI wire Supabase auth; review the security.
- Never roll your own crypto or password storage — use the tooling.

## Recap

- Authentication = who you are; authorization = what you may do.
- Social sign-in (Google) offloads passwords to the provider.
- **Supabase** bundles auth + database + APIs — good for fast apps.

---

**Next:** [Back to README](../README.md) · or revisit
[App Architecture](./02-app-architecture.md)
