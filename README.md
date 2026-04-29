# ⚡ Kristen — Work Chief of Staff

Kristen is a production AI agent that manages the operational layer of a demanding professional role. She handles morning briefings, meeting note processing, priority tracking, workflow design, team coordination, and follow-up systems — built around the principle that durable structure beats one-off heroics.

This isn't a demo. Kristen has been running daily since early 2026.

---

## Architecture

Kristen is one agent in a multi-agent system, focused exclusively on work operations:

```
┌─────────────────────────────────────────────────────────┐
│                     Multi-Agent System                  │
├──────────────┬──────────────────┬───────────────────────┤
│    Frank     │     Kristen      │        Heidi          │
│  (Ops Agent) │ (Work Chief of   │  (Home Chief of Staff)│
│              │    Staff)        │                       │
├──────────────┼──────────────────┼───────────────────────┤
│ Resets       │ Work operations  │ Home + personal ops   │
│ Kristen's    │ Morning briefs   │ Email, calendar,      │
│ session at   │ Meeting notes    │ meal planning, CRM    │
│ 3 AM daily   │ Priority mgmt    │                       │
│              │ Workflow design  │                       │
│              │ Team tracking    │                       │
└──────────────┴──────────────────┴───────────────────────┘
```

**Frank** runs a nightly session reset at 3 AM, keeping Kristen's context lean and costs predictable.

**Shared state** lives in workspace files (`MEMORY.md`, `SYSTEMS.md`, `ops/`) — not in session history. Files are truth; session history is temporary.

---

## What Kristen Does

### Daily Operations
- **Morning brief** (triggered by "good morning"): priority list for the day, calendar flags requiring prep, team region check, one live AI industry story
- **Meeting note intake**: processes notes from [MEETING TOOL], extracts actions, updates people directory, flags owner changes
- **Priority tracking**: cross-references open items, calendar, and waiting-fors into a clear daily list

### Workflow & Systems
- Maps recurring friction into repeatable systems
- Drafts SOPs, templates, agendas, status updates, onboarding docs
- Identifies what to automate, delegate, standardize, or stop
- Structures new work: scope, owner, milestones, dependencies, immediate next actions

### Tracking & Accountability
- Open loops, commitments, and waiting-fors — nothing relies on memory alone
- People directory: tracks team context, recent interactions, owner changes
- Brag list: running log of wins and contributions for performance cycles

---

## File Structure

```
kristen/
├── AGENTS.md          # Workspace hierarchy, memory rules, operating protocols
├── SOUL.md            # Identity, values, working style, operating principles
├── IDENTITY.md        # Name, role, tone, vibe
├── HEARTBEAT.md       # Trigger logic — what to check and when
├── SYSTEMS.md         # Step-by-step procedures for every recurring workflow
├── TOOLS.md           # Endpoints, resource references, tool stack
├── USE-CASES.md       # What this agent is built to do
├── MEMORY.md          # Curated long-term memory (stub — private in production)
└── ops/
    ├── brag-list.md   # Running log of wins (stub)
    ├── people.md      # Team directory (stub — real data is private)
    └── waiting.md     # Waiting-for tracker (stub)
```

---

## Design Principles

**Files are memory, not session history.** Kristen wakes up fresh every session. Continuity comes from well-maintained files — `MEMORY.md`, daily notes, `SYSTEMS.md`, `ops/`. Session history is dead weight; writing things down is the discipline that makes the whole system reliable.

**No narration.** Kristen does the work and reports the outcome. No "Let me check that..." — just the result.

**Decisions over options.** The job is to reduce cognitive load. Kristen makes the call when she has enough context. She asks when she genuinely doesn't.

**Durable systems over one-off heroics.** A repeatable workflow built on a chaotic Tuesday is worth more than a perfect system that requires calm. Kristen is designed for the actual texture of a fast-moving role.

**Discretion by default.** Employer, team, and project data stays private. This repo contains the architecture and philosophy — not the operational content.

---

## Tech Stack

- **Agent framework:** Claude (Anthropic) via [OpenClaw](https://openclaw.ai) 🦞
- **Session management:** Frank (custom ops agent) — nightly reset + context re-injection
- **Meeting notes:** [MEETING TOOL] (tool-agnostic — bring your own)
- **Integrations:** Apple Reminders, calendar, docs
- **Primary channel:** Telegram
- **Language:** Markdown (workspace files)

---

## What's Not In This Repo

- `memory/` — raw daily session notes. Personal logs, not for public consumption.
- `scripts/` — internal automation scripts. Implementation detail, not part of the template.
- `USER.md` — private context about the operator.
- `redact.json` — sync and redaction config. Internal tooling.
- Real content in `ops/` — the stubs show structure; actual people, projects, and wins are private.

The architecture, philosophy, and operational patterns are all here. The employer-specific content isn't.

---

## Status (April 2026)

Kristen is in active daily use for work operations. Integrations: Apple Reminders, calendar, [MEETING TOOL] for meeting note intake.

---

*Built with Claude (Anthropic) + [OpenClaw](https://openclaw.ai) 🦞. Clarity over clutter, always.*
