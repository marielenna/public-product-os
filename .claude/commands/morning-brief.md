---
name: morning-brief
description: >
  Proactive session opener. Queries Superhuman (mail + calendar), Granola meeting notes,
  tasks.md, context/, projects/, Jira via Zapier MCP, and Coda. Builds a sharp daily brief
  with organized priorities. No questions asked. Use when the user says "morning brief",
  "what's on my plate", "daily brief", "start my day", or runs /morning-brief.
argument-hint: "[focus area]"
---

# /morning-brief

Generate a daily briefing by querying all connected sources with smart, targeted prompts. Do not ask questions — synthesize everything and present it. Feel like a trusted colleague who came in early and did the homework.

**Works with no arguments.** Designed to run cold.

---

## Usage

```
/morning-brief
```

## Step 1 — Stream Progress
Output: "Pulling together your morning brief..."

## Step 2 — Load Local Context

Read the following files to ground the brief in what's already known:

- `tasks.md` — Active, In Progress, Waiting On, and Done sections
- `context/team_goals.md` — team goals and current quarter priorities
- `context/sprint_status.md` — sprint status and blockers
- `context/team_overview.md` — team roster and stakeholders

Also scan `projects/` — check for any project folders with recent files (modified in last 7 days). Note active projects and any that appear stalled.

> "Reading your tasks, goals, and project notes..."

## Step 3 — Query Connected Sources (In Parallel)

Track successes and failures for the source footer.

### Superhuman — Email
> "Scanning your inbox..."

**Smart prompt strategy:**
1. Pull unread emails from Superhuman MCP
2. Prioritize: (a) sender is a known stakeholder or team member, (b) time-sensitive subject ("urgent", "action required", "EOD", "please review", "approval needed", "deadline"), (c) To: field over CC:
3. Group: time-sensitive first, then stakeholder, then others

**Surface:** Total unread count. Up to 5 highlighted: sender, subject, one-line preview. Flag time-sensitive ones.

> If Superhuman MCP is not connected: skip email section, note in footer.

### Superhuman — Calendar
> "Looking at your schedule today..."

**Smart prompt strategy:**
1. Pull today's events from Superhuman MCP: titles, times, attendees
2. Flag meetings with exec stakeholders (cross-reference names in `context/team_overview.md`)
3. Note back-to-back blocks or meetings without a prep buffer
4. Surface any free blocks of 90+ minutes

**Surface:** Ordered list with times. Flag exec meetings with ⚡. Note free blocks if relevant.

> If Superhuman MCP is not connected: skip calendar section, note in footer.

### Granola — Recent Meetings
> "Checking your recent meetings for action items..."

**Smart prompt strategy:**
1. List meetings from last 48 hours via Granola MCP
2. Cross-reference against `meetings/` directory for any that haven't been synced yet
3. For synced meetings, scan for open action items assigned to you

**Surface:** Unsynced meetings (count + titles). Open action items from recent notes. Flag anything that's been sitting more than 3 days without follow-through.

> If Granola MCP is not connected: scan `meetings/` directly for files dated in the last 48 hours and surface action items from those.

### Jira — Active Sprint
> "Scanning your sprint tickets..."

**Smart prompt strategy (via Zapier MCP):**
1. Pull Jira issues in the active sprint assigned to current user
2. Flag: overdue (by days), blocked (include blocker description), due within 3 days
3. Also surface any tickets being watched that are blocked

**Surface:** Overdue with ticket ID/title/days late. Blocked with one-line blocker. Upcoming deadlines.

> If Zapier MCP is not connected: skip Jira section, note in footer. Pull any Jira-related items from tasks.md Waiting On section instead.

### Coda — Document Updates
> "Checking for recent Coda updates..."

**Smart prompt strategy:**
1. Search Coda for pages updated in the last 48 hours related to active projects
2. Focus on projects listed in `context/team_goals.md`

**Surface:** Which docs updated, by whom, when. One-line summary if available.

> If Coda MCP is not connected: skip this section.

### Slack — Mentions and DMs
> "Checking Slack for anything that needs your attention..."

**Smart prompt strategy:**
1. Search for messages where you are @mentioned in the last 24-48 hours
2. Filter: messages you have NOT replied to
3. Prioritize: (a) senders who are exec stakeholders or team leads, (b) urgent language ("urgent", "ASAP", "blocker", "waiting on you", "EOD"), (c) DMs over channel messages

**Surface:** Up to 5 unanswered mentions: sender, channel/DM, one-line snippet.

> If Slack MCP is not connected: skip @mentions section, note in footer.

## Step 4 — Synthesize and Present

Format (adapt — NEVER show empty sections):

```
Good morning. Here's where things stand.

TODAY'S MEETINGS
• [time] — [title] with [key attendees]
• [time] — [title] ⚡ [flag if exec meeting]
[Light day note if calendar is sparse]

NEEDS YOUR ATTENTION
• 📧 Email: [sender] — "[subject]" (unread, time-sensitive)
• 💬 Slack: [sender] in [#channel] — "[snippet]" (unanswered, [time ago])
• 🎫 Jira: [TICKET-ID] "[title]" is [N] days overdue
• 🎫 Jira: [TICKET-ID] "[title]" is blocked — [blocker summary]

RECENT MEETING FOLLOW-UPS
• [action item] from [meeting title] ([date])
• [N] meetings not yet synced to meetings/ — [titles]

OPEN ITEMS (from tasks.md)
• [Active item that's been open and may need a nudge]
• [Waiting On item that's been waiting more than 5 days]

TODAY'S PRIORITIES
1. [Most important — one-line reason tied to goals or calendar]
2. [Second priority]
3. [Third priority]

[HEADS UP — max 1 proactive observation, only if genuinely worth flagging]
• [e.g., "PROJ-47 has been blocked for 2 weeks — worth escalating?"]

---
Sources used: [list]
Staged (not yet connected): [list]
```

## Tone Rules
- Warm but efficient — trusted colleague, not a status bot
- Specific over generic — "PROJ-47 is 6 days overdue" not "you have overdue tickets"
- One proactive insight max in Heads Up
- No padding — light day: "Light day — good time to get ahead on [specific thing]."
- Never show empty sections
- Source footer ALWAYS present — separate connected sources from staged ones

## Fallback Behavior

| Missing | Behavior |
|---------|----------|
| Superhuman not connected | Skip email + calendar sections; note in footer |
| Slack not connected | Skip @mentions; note in footer as staged |
| Granola not connected | Scan meetings/ directly for last 48 hours |
| Zapier/Jira not connected | Pull Jira-related items from tasks.md Waiting On; note in footer as staged |
| Coda not connected | Skip document updates |
| tasks.md empty | "No open tasks found — update tasks.md to get better briefs." |
| Everything unavailable | "Still getting set up — here's what I know from local files." Then surface tasks.md and context/ only. |
