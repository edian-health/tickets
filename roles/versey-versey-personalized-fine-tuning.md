# Set Up Personalized Fine-Tuning on Versey

**Company:** [Versey](../companies/versey.md)
**Type:** Engineering — Fractional, ~3–4 days
**Rate:** $70–95/hr (senior ML/backend contractor, London/remote market)
**Location:** Remote (London-friendly hours)
**Stack:** fireworks, next.js, react, braintrust, typescript
**Status:** Open

---

Wire up per-user fine-tuning on Versey: users drop in reference files, we fine-tune a small model on Fireworks so the app can write in their voice. Evals via Braintrust. The hard part is keeping cost and performance observable as concurrent fine-tunes scale.

**Stakeholder:** [Will Taylor, CEO](https://www.linkedin.com/in/wrftaylor/)

**Minimum earning per ticket:** $1.5k

**Estimated hours:** ~3–4 days

## What you'd build

Per-user fine-tuning on Versey. A user uploads a set of reference files (their writing samples), we kick off a fine-tune of a small model on Fireworks, and the app then generates in that user's voice. The Next.js/React product side already exists; Braintrust is set up for evals. You'd own the fine-tuning pipeline end to end — file ingestion → Fireworks job → eval → routing the user to their model.

## The hard part

The hard part: making cost and performance observable in a way that scales when many users fine-tune at once. Per-user fine-tunes are cheap individually and ugly in aggregate — concurrent jobs, queueing, eval cost, inference cost per user, model cold-starts. We need to know what each user costs and how their model performs, without hand-rolling a dashboard for every metric.

## What's in it for you

- Self-managed work — you own the architecture decisions, not someone else's ticket
- Fireworks + Braintrust + Next.js, no legacy to fight
- Successful trial → ongoing fractional work with Versey

## What we're looking for

- Shipped production fine-tuning pipelines before (any provider — Fireworks experience is a plus, not required)
- Comfortable instrumenting cost and latency in a multi-tenant setup
- Has used Braintrust or an equivalent (Langfuse, Phoenix, Arize) for LLM evals
- TypeScript / Next.js fluent

## First ticket

Dive in and set up the pipeline end to end: a user can drop reference files, a fine-tune runs on Fireworks, evals run in Braintrust, and the user can generate against their model in the app. Cost and performance metrics are queryable per user. Sketches in Figma and the Versey repo are waiting for you on day one.

## How to apply

All roles on Tickets use the universal `tickets-apply` skill, run from inside Claude Code. Standard install:

```bash
mkdir -p ~/.claude/skills/tickets-apply
curl -fsSL https://raw.githubusercontent.com/edian-health/tickets/main/skills/tickets-apply/SKILL.md \
  -o ~/.claude/skills/tickets-apply/SKILL.md
```

Then in Claude Code:

```
Apply to versey-versey-personalized-fine-tuning on Tickets
```
