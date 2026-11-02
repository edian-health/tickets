---
name: tickets-help
description: Get help with anything Tickets–related — billing, applications, listings, manage tokens, payouts, references, anything you're stuck on. Routes the question to the Tickets helpdesk, which answers from the public knowledge base or escalates to a human via Slack when it can't (or shouldn't) answer alone. Use whenever the user says "ask support", "ask the team", "I have a question about Tickets", "how do I X on Tickets", or otherwise needs help that isn't covered by another tickets-* skill.
---

# Tickets - helpdesk

> Not active yet. The helpdesk endpoint is not in the production backend. Do not submit help requests through this skill until that deployment has been verified. No response-time promise applies while inactive.

You are routing the user's question to the **Tickets helpdesk** at `https://app.tckts.work/api/help`.

This skill is a thin client. The backend agent does the work — answers what it can from the knowledge base, escalates the rest to a human on Slack. You collect the question, post it, and relay the response.

## Step 1 — Frame the question

Ask the user what they need help with, if it isn't already clear. Prompt for:

- **What they're trying to do** (the goal, not just the symptom)
- **What they've tried** (if anything)
- **Any role slug, application id, manage token id, or company slug** that's relevant — but only if they volunteer it. Do not fish for personal data.

Keep it to one or two short messages. Don't run a form.

## Step 2 — Strip candidate-side context

The helpdesk agent **must not** see candidate identity or pitch content. Before you POST:

- Do not include the candidate's `name`, `email`, `github`, `linkedin`, `portfolio`, `cv_url`, `pitch`, or `notes` from `~/.claude/skills/tickets-profile/profile.json`.
- If the user pastes their own pitch or CV link asking for help, redact it to `<candidate content omitted>` and tell them you've done so. The helpdesk doesn't need it; if a human does, the escalation path will reach back to the user directly.
- Application ids and role slugs are fine — they're public references, not identity.

If the user pushes back ("but I want them to see it"), tell them to email `help@tckts.work` directly with a fresh thread.

## Step 3 — POST to the helpdesk

```bash
curl -X POST https://app.tckts.work/api/help \
  -H "Content-Type: application/json" \
  -d '{
    "question": "...",
    "context": {
      "role_slug": "...",        // optional
      "application_id": "...",   // optional
      "company_slug": "...",     // optional
      "manage_token_hint": "..." // optional, last 4 chars only
    },
    "audience": "candidate" | "employer" | "unknown"
  }'
```

`audience` is your best guess from the conversation — the agent uses it to pick tone and which KB sections to draw from. Default to `unknown` if you genuinely can't tell.

The response is one of:

```json
{ "ok": true, "answered": true,  "answer_md": "...", "sources": [{"title": "...", "url": "..."}] }
{ "ok": true, "answered": false, "ticket_id": "...", "eta_hours": 24, "reason": "..." }
```

## Step 4 — Relay

- **Answered:** show the `answer_md` verbatim, then list `sources` as a short footer. Don't paraphrase — the agent's wording was chosen for accuracy.
- **Escalated:** tell the user a human will follow up, give the `ticket_id`, the `eta_hours`, and the short `reason` the agent gave. Ask for the best email to reach them on if you don't already have it from the conversation, and re-POST with `context.reply_email` set.

If the API returns 5xx, retry once. If still failing, tell the user and point them at `help@tckts.work`.

## Step 5 — Follow-ups

If the user replies with a clarification or a follow-up question, POST again with `context.thread_id` from the previous response. The agent threads on its side and re-uses prior context — you don't need to re-summarize.

## Tone

- Brief. The user came here with a problem; don't pad the answer.
- Don't pretend to know the answer yourself. This skill exists because the helpdesk agent is the source of truth.
- If the helpdesk escalates, don't editorialize on why — just relay the reason it gave.

## Edge cases

- **User asks something this skill obviously can't help with** (e.g. "write me a pitch"): say so and point them at the right `tickets-*` skill.
- **User is mid-application:** finish the application via `tickets-apply` first if they want; help questions can wait or run in parallel in a separate turn.
- **User reports a bug or outage:** still POST it — the helpdesk agent will escalate hard outages immediately.
- **User asks for someone's contact info / private data:** refuse and tell them to email `help@tckts.work`.
