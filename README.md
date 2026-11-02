<div align="center">

# Tickets <img width="33" height="33" alt="Gemini_Generated_Image_6j8i0m6j8i0m6j8i-removebg-preview" src="https://github.com/user-attachments/assets/b8a266fe-9c6c-45d9-8e09-423b2a023540" /> 

**The fractional talent marketplace for AI-native people.**

Post projects, or apply, by chatting with Claude Code. Paid fairly at market rates.

![Rates verified](https://img.shields.io/badge/rates-verified%20against%20levels.fyi-2da44e?style=flat-square) ![Platform fees](https://img.shields.io/badge/platform%20fees-none-0969da?style=flat-square) ![Recruiters](https://img.shields.io/badge/recruiters-none-8957e5?style=flat-square)

[Browse open roles ↓](#open-roles) · [Install in Claude](#install) · [Hiring philosophy](./guides/hiring-philosophy/README.md)

_You're absolutely hired!_

</div>

---

## How it works

| For candidates                                                           | For employers                                                                    |
| :----------------------------------------------------------------------- | :------------------------------------------------------------------------------- |
| **1. Apply** — in seconds via `Apply to <role>` in Claude Code.          | **1. Post free** — describe your role to Claude Code, it shapes up your listing. |
| **2. Get matched** — set your stack once; we email you when a role fits. | **2. Match** — subscribers whose stack matches yours get alerted automatically.  |
| **3. Get hired** — employers reply straight from the email.              | **3. Hire** — every applicant lands directly in your inbox.                      |

---

## Open Roles

<!-- TICKETS_OPEN_ROLES_START -->

**0 open roles** · last updated 2026-11-02

_No roles open right now._

<details>
<summary>Archived roles (9)</summary>

These listings were archived on 2026-11-02. They are kept for reference and are not accepting applications. Historical rates and terms below are not current offers.

| Role                                                                                                     | Company    | Type                                                               | Hourly rate                                            |
| -------------------------------------------------------------------------------------------------------- | ---------- | ------------------------------------------------------------------ | ------------------------------------------------------ |
| [Set Up Personalized Fine-Tuning on Versey](./roles/versey-versey-personalized-fine-tuning.md)           | Versey     | Engineering — Fractional, ~3–4 days                                | $70–95/hr   |
| [Set Up the Versey Slack Community + Automations](./roles/versey-slack-community.md)                     | Versey     | Engineering — Operations / Community Engineering                   | $45–75/hr   |
| [Design and Build Versey's New Onboarding Flow](./roles/versey-onboarding-flow.md)                       | Versey     | Design — Product + Design + Engineering                            | $70–100/hr  |
| [Build Interactive Tutorials for the Versey App](./roles/versey-interactive-tutorials.md)                | Versey     | Design — Product + Design + Frontend                               | $50–80/hr   |
| ~~[Build the Versey Homepage in Astro from a Figma Design](./roles/versey-homepage-astro.md)~~ — _taken_ | ~~Versey~~ | ~~Engineering — Frontend Engineering~~                             | ~~$45–75/hr~~ |
| [Add Conversion Animations to the Versey Homepage](./roles/versey-homepage-animations.md)                | Versey     | Design — Design + Frontend                                         | $55–85/hr   |
| [Automate Tickets' Hiring Backend + Outreach](./roles/tickets-hiring-platform.md)                        | Tickets    | Engineering — Applied AI Engineering · ongoing, ~5–20 hrs/week     | $75–100/hr  |
| [Build a Creators Use-Case Sub-Page on Versey.ai](./roles/versey-creators-page.md)                       | Versey     | Design — Frontend + Copy + Design                                  | $50–80/hr   |
| [Build the Claude → Versey Handoff Feature](./roles/versey-claude-handoff.md)                            | Versey     | Product — Backend + Product Engineering                            | $75–100/hr  |

</details>

<!-- TICKETS_OPEN_ROLES_END -->

_By using Tickets, you agree to our ground rules — [for candidates](./CANDIDATE_RULES.md), [for employers](./EMPLOYER_RULES.md)._

---

## Install

In Claude Code, paste:

```
install the skills from this repo https://github.com/edian-health/tickets
```

That installs all seven skills below. Then talk to Claude in plain English — `Which roles are on tickets atm?`, `Apply to <role url>`, `Post a role on Tickets`, etc.

| Skill                     | What it does                                                                 |
| ------------------------- | ---------------------------------------------------------------------------- |
| `tickets-profile`   | Set up your candidate profile (used to filter and pre-fill everything else). |
| `tickets-list`      | Browse open roles, filtered to your stack.                                   |
| `tickets-apply`     | Submit a tailored application to any role.                                   |
| `tickets-subscribe` | Email alerts for new roles that match your profile.                          |
| `tickets-post`      | Post a project (employers — free, no recruiter fees).                        |
| `tickets-manage`    | Edit, pause, close, or reopen a role you posted.                             |
| `tickets-help`      | Helpdesk client, inactive until the backend helpdesk is deployed and verified. |

<details>
<summary>Manual install — one curl per skill</summary>

```bash
mkdir -p ~/.claude/skills/tickets-profile
curl -fsSL https://raw.githubusercontent.com/edian-health/tickets/main/skills/tickets-profile/SKILL.md \
  -o ~/.claude/skills/tickets-profile/SKILL.md

mkdir -p ~/.claude/skills/tickets-list
curl -fsSL https://raw.githubusercontent.com/edian-health/tickets/main/skills/tickets-list/SKILL.md \
  -o ~/.claude/skills/tickets-list/SKILL.md

mkdir -p ~/.claude/skills/tickets-apply
curl -fsSL https://raw.githubusercontent.com/edian-health/tickets/main/skills/tickets-apply/SKILL.md \
  -o ~/.claude/skills/tickets-apply/SKILL.md

mkdir -p ~/.claude/skills/tickets-subscribe
curl -fsSL https://raw.githubusercontent.com/edian-health/tickets/main/skills/tickets-subscribe/SKILL.md \
  -o ~/.claude/skills/tickets-subscribe/SKILL.md

mkdir -p ~/.claude/skills/tickets-post
curl -fsSL https://raw.githubusercontent.com/edian-health/tickets/main/skills/tickets-post/SKILL.md \
  -o ~/.claude/skills/tickets-post/SKILL.md

mkdir -p ~/.claude/skills/tickets-manage
curl -fsSL https://raw.githubusercontent.com/edian-health/tickets/main/skills/tickets-manage/SKILL.md \
  -o ~/.claude/skills/tickets-manage/SKILL.md

mkdir -p ~/.claude/skills/tickets-help
curl -fsSL https://raw.githubusercontent.com/edian-health/tickets/main/skills/tickets-help/SKILL.md \
  -o ~/.claude/skills/tickets-help/SKILL.md
```

</details>

---

## About

Built by the ex-founders of [Rota](https://rota.com) — one of the UK's largest on-demand temporary staffing platforms, running ~3,000 placements a week. Tickets is what we'd build for the AI-fluent end of that market: a marketplace, smaller, faster, more agenty.

## On rates

SF rates where the level warrants, London/remote rates where it doesn't. Every role is benchmarked against levels.fyi for the matching seniority and location; early-stage roles get priced honestly for what the work needs, not padded to a headline number.

---

## License

MIT. Fork it, run your own list.
