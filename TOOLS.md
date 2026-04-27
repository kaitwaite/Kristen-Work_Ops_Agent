# TOOLS.md — Kristen's Tool Reference

---

## Apple Reminders — ⚡ Work To-Dos

The live source of truth for [OWNER]'s active work tasks.
List name: ⚡ Work To-Dos · Location: Heidi's iCloud, Mac mini

Read open items:

```applescript
osascript << 'SCRIPT'
tell application "Reminders"
  try
    set theList to list "⚡ Work To-Dos"
    set openItems to every reminder in theList whose completed is false
    set output to ""
    repeat with r in openItems
      set output to output & "• " & (name of r as string) & return
    end repeat
    return output
  on error errMsg
    return "Error reading Reminders: " & errMsg
  end try
end tell
SCRIPT
```

Notes:
- completed is false = open; completed is true = done
- Phone checkmarks sync back to Mac mini correctly — done:true is reliable
- ops/actions.md is a supplemental reference file, not a task source

---

## News Feeds — Morning Brief

### AI Story (The Guardian)
```
curl "https://content.guardianapis.com/search?q=artificial+intelligence&show-fields=headline,trailText&page-size=5&order-by=newest&api-key=test"
```
Pick the most relevant result for [OWNER]'s work context. One paragraph max. Not doomscroll.

### Team Region Check

**Iran (Tehran + northern)** — [DM1]'s aunt; [DM3]'s parents + brother
```
curl "https://feeds.bbci.co.uk/news/world/middle_east/rss.xml"
```
Filter for Iran-relevant titles. Report only if genuinely significant.

**Guadalajara + Aguascalientes** — [STAKEHOLDER], [DM4], [DM5], [DM6], [DM9], [DM7], [DM8]
```
curl "https://content.guardianapis.com/search?q=Guadalajara+OR+Aguascalientes+Mexico&show-fields=headline&page-size=3&order-by=newest&api-key=test"
```
Supplement with web_fetch on Mexico news if results are thin.

**Los Angeles** — [DM1], [DM3], [MANAGER], [SKIP-LEVEL]
```
curl "https://content.guardianapis.com/search?q=Los+Angeles&show-fields=headline&page-size=3&order-by=newest&api-key=test"
```

**New York** — [NEW HIRE]
```
curl "https://content.guardianapis.com/search?q=New+York&show-fields=headline&page-size=3&order-by=newest&api-key=test"
```

**New Jersey** — [DM10]
```
curl "https://content.guardianapis.com/search?q=New+Jersey&show-fields=headline&page-size=3&order-by=newest&api-key=test"
```

One line per region max. Only report if something is genuinely significant for the named person.
Empathy radar, not anxiety feed.

---

## [MEETING TOOL]

[OWNER]'s meeting transcription tool.
Extraction prompt lives at: systems/granola-prompt.md
[OWNER] runs the "Yesterday" filter in [MEETING TOOL] during the morning brief to capture prior day's meetings.
Output → paste to Kristen → extract actions/decisions/waiting-fors → update ops/ files.

---

## ops/ File Map

```
ops/people.md           — Stakeholder directory + voice aliases
ops/waiting.md          — Items delegated out, awaiting response
ops/actions.md          — Context notes + reference snapshot (NOT live task source)
ops/morning-brief.md    — Morning brief workflow steps
ops/brag-list.md        — [OWNER]'s wins for leadership visibility
ops/reminders.md        — Scheduled follow-up dates
ops/meeting-notes/      — Archived [MEETING TOOL] extracts
ops/onboarding-kamilah/ — [NEW HIRE] Francis onboarding package
```
