# SYSTEMS.md — How We Run Things

_This file documents step-by-step procedures for every recurring workflow._
_Triggers and timing live in HEARTBEAT.md. Commands and endpoints live in TOOLS.md._

---

## 🌅 Morning Brief
**When:** [OWNER] says "good morning" (see HEARTBEAT.md)

1. Ask for yesterday's [MEETING TOOL] notes (Friday's if Monday). Process when received — see [MEETING TOOL] Note Processing below.
2. Read Apple Reminders (⚡ Work To-Dos) via osascript (see TOOLS.md). Note what's due today or overdue.
3. Cross-reference open tasks with any calendar context [OWNER] provides. Surface the top 3–5 items.
4. Fetch one AI story from The Guardian (see TOOLS.md). One paragraph max. Interesting and useful for [OWNER]'s work context. Not doomscroll.
5. Fetch team region headlines (see TOOLS.md). Report only if something is genuinely significant for a named team member. One line per region max. Empathy radar, not anxiety feed.
6. Deliver the full brief to [OWNER]. Then, at the END, ask for updates or new items. Never wait for a response before delivering.

---

## 📋 [MEETING TOOL] Note Processing
**When:** [OWNER] sends a [MEETING TOOL] extract (morning or ad hoc)

Extraction prompt for [OWNER] to paste into her meeting tool: `systems/meeting-notes-prompt.md`

1. Parse the extract for:
   - [OWNER]'s actions → add to Apple Reminders (⚡ Work To-Dos)
   - Others' actions → add to ops/waiting.md with person + what + expected date
   - Decisions made → note in ops/meeting-notes/YYYY-MM-DD.md
   - Open questions → flag to [OWNER] if time-sensitive
   - People or alias corrections → update ops/people.md
2. Save full processed extract to ops/meeting-notes/YYYY-MM-DD.md
3. Summarize back to [OWNER]: what was added, what changed, anything needing attention.

---

## 📰 [SKIP-LEVEL] Newsletter
**When:** Weekly — [OWNER] initiates

Structure: Shared Services → Measurement & Insights → Communications Platform → Cross-Team Initiatives
Format: short, bullet-heavy, links inline, warm opener, no asks
Reference: [OWNER]'s sent Apr 24 version is the locked template

Draft → [OWNER] reviews and approves → send

---

## 📢 Team Newsletter — "The Download"
**When:** Every Friday — [OWNER] initiates

Audience: [OWNER]'s direct reports only
Format: casual, bullet points only, emoji section headers
Purpose: visibility bridge — things [OWNER] hears that the team doesn't yet know

Draft → [OWNER] reviews and approves → send

---

## 📁 Ops File Maintenance
**When:** After every [MEETING TOOL] session or substantive conversation

| File | Update when |
|------|-------------|
| ops/waiting.md | New delegated items; when items resolve |
| ops/people.md | New stakeholders added; voice alias corrections |
| ops/brag-list.md | A notable win happens |
| ops/meeting-notes/ | After each [MEETING TOOL] processing session |
| ops/onboarding-kamilah/ | As [NEW HIRE]'s onboarding progresses |
| memory/YYYY-MM-DD.md | End of session — what changed, decisions made |
