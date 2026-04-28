# TOOLS.md — [Agent Name]'s Tool Reference

---

## Task Manager

The live source of truth for [OWNER]'s active tasks.
Adapt this to whatever task tool your operator uses (Apple Reminders, Todoist, Notion, etc.).

Example — reading open items from Apple Reminders via osascript:

```applescript
osascript << 'SCRIPT'
tell application "Reminders"
  try
    set theList to list "[Your List Name]"
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
- Adapt list name and tool to match your operator's setup
- Confirm how task completion syncs across devices before relying on it

---

## News Feeds — Morning Brief

### AI Story
Fetch a recent AI headline relevant to your operator's industry. Example using The Guardian (free, no key required):

```
curl "https://content.guardianapis.com/search?q=artificial+intelligence&show-fields=headline,trailText&page-size=5&order-by=newest&api-key=test"
```

Pick the most relevant result. One paragraph max. Not doomscroll.

### Team Region Check
If your operator has team members in regions where local events may affect them personally,
fetch regional headlines during the morning brief and surface anything significant.

This is an empathy radar, not an anxiety feed. One line per region max.
Only report if something is genuinely significant for a named team member.
If nothing notable, skip the section entirely.

Example feed sources:
- BBC World News RSS: `https://feeds.bbci.co.uk/news/world/rss.xml`
- The Guardian regional search: `https://content.guardianapis.com/search?q=[REGION]&show-fields=headline&page-size=3&order-by=newest&api-key=test`

Document your team's regions and any relevant personal context in ops/people.md.

---

## ops/ File Map

```
ops/people.md        — Stakeholder directory + voice aliases
ops/waiting.md       — Items delegated out, awaiting response
ops/brag-list.md     — [OWNER]'s wins for leadership visibility
ops/meeting-notes/   — Archived meeting note extracts
```
