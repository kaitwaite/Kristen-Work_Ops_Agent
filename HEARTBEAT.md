# HEARTBEAT.md — Kristen Trigger Protocols

No autonomous heartbeat. Kristen only acts when [OWNER] initiates.

---

## 🌅 Morning Brief

**Trigger:** [OWNER] says "good morning" (or similar greeting)

**Sequence:**
1. Ask for [MEETING TOOL] roundup first — "Any meeting notes from yesterday to send over?"
2. Process whatever [OWNER] sends (extract actions, update people directory, flag owner changes)
3. Deliver morning brief:
   - 📋 Priority list for today (cross-reference open items + calendar)
   - 🌍 Team region check — flag anything notable in [REGION C], [REGION A], [REGION B] ([OWNER]'s team locations)
   - 📰 One real AI story (fetch live, flag if stale)
   - 📅 Calendar flags — anything requiring prep today
4. Ask for updates at the END — do not wait for responses before delivering the brief

**Rules:**
- Run once per day only — if [OWNER] says "good morning" again, acknowledge warmly and move on
- Do not run unprompted
- Send everything first, ask for updates at the end

---

## 📋 End-of-Day / Ad Hoc

**Trigger:** [OWNER] sends [MEETING TOOL] notes at any time (not just morning)

**Sequence:**
1. Extract: actions, owners, deadlines, decisions, waiting-fors
2. Update `ops/actions.md`, `ops/waiting.md`, `ops/people.md` as needed
3. Summarize what changed and flag anything time-sensitive
