# Weekly Planning Workflow

Run this every Monday morning to set up your week.

## Overview

| Step | Time | Output |
|------|------|--------|
| 1. Review last week | 15 min | Wins, learnings, action items (mail + meeting notes + tasks) |
| 2. Check goals | 5 min | Goal alignment |
| 3. Jira sprint check | 5 min | Sprint health, blocked items flagged |
| 4. Product dashboard | 10 min | Usage, errors, and trends with Fullstory links |
| 5. Identify priorities | 10 min | Top 3 for the week + tasks.md updated |

**Total:** ~45 minutes

> **MCP Status:** This workflow uses the following MCP integrations. If not yet connected, those steps include a fallback.
> - **Superhuman MCP** — mail and calendar review (Steps 1, 5)
> - **Zapier MCP** — Jira sprint status (Step 3)
> - **Fullstory MCP** — product usage dashboard (Step 4)
>
> To connect: In a Claude session, ask Claude to authenticate the relevant MCP.

---

## Step 1: Review Last Week

**First, review last week's mail and calendar via Superhuman MCP:**
> If Superhuman MCP is not connected, skip to meeting notes below.

```
Use the Superhuman MCP to pull last week's emails and calendar events. Summarize key threads that need follow-up and meetings that generated decisions or next steps.
```

**Then, review last week's meeting notes for action items:**

Scan `meetings/` for files dated in the prior week. Ask Claude:
```
Read the meeting notes in meetings/ from last week. Identify any action items assigned to me and flag anything that hasn't been captured in tasks.md yet.
```

**Also check `tasks.md`:**
```
Review tasks.md — specifically the Active, In Progress, and Waiting On sections. What carried over from last week?
```

**Look at:**
- What shipped?
- What slipped? Why?
- What did I learn?
- What feedback did I get?

---

## Step 2: Check Goals

**Reference:** `context/department_level_goals.md`, `context/team_goals.md`, `context/sprint_status.md`

Ask:
- Are we on track for quarterly goals?
- Any goal at risk?
- What moved the needle last week?

**Prompt:**
```
Compare my progress against `context/department_level_goals.md`, `context/team_goals.md`, and `context/sprint_status.md`. What's on track, at risk, or blocked?
```

---

## Step 3: Jira Sprint Check

**Pull your active sprint via Zapier MCP:**
> If Zapier MCP is not connected, skip this step and check Jira directly.

```
Use the Zapier MCP to pull Jira issues in my active sprint. List them by status. Flag anything that's blocked, overdue, or unassigned.
```

Review:
- What's in-flight vs. stalled?
- Any issues that need my attention before end of sprint?
- Anything to raise in standup or with the team?

---

## Step 4: Product Dashboard

**Pull product usage from Fullstory MCP:**
> If Fullstory MCP is not connected, skip this step. Uses the `/fullstory-general-analysis` skill.

Run the following three queries in sequence. Each should return a `metric_url` — save all three links for reference.

**1. Active Users (last 14 days)**
```
Use the fullstory-general-analysis skill to find the count of active users on [your product] in the last 14 days. Search for an existing metric first. Time range: last_14_days. Return the metric_url.
```

**2. Error Encounters**
```
Use the fullstory-general-analysis skill to find how many users encountered error messages in [your product] in the last 14 days, and what the most common errors were. Search for existing error metrics first. Use a top_n breakdown by error message. Time range: last_14_days. Return the metric_url.
```

**3. Top 3 Trends**
```
Use the fullstory-general-analysis skill to identify the top 3 behavioral trends in [your product] over the last 14 days — look at trend metrics for things like session length, feature usage, drop-off points, or engagement patterns. Return a trend metric for each with metric_url links.
```

**Review:**
- Is active user count growing, flat, or declining week-over-week?
- Which error is most common — is it known or a new signal?
- Do any trends suggest a feature or flow that needs attention this week?

> If Fullstory MCP is not connected: note "dashboard skipped — Fullstory MCP not connected" and move to Step 5.

---

## Step 5: Identify Priorities

**Pull this week's calendar via Superhuman MCP:**
> If Superhuman MCP is not connected, reference your calendar manually.

```
Use the Superhuman MCP to show this week's calendar events. What are the key meetings, deadlines, and stakeholder touchpoints?
```

This grounds your Top 3 in what's actually happening this week.

**Reference `tasks.md`** for any carried-over items before finalizing.

Pick your **Top 3** for the week:
1. Most important outcome
2. Second most important
3. Third priority

**Rules:**
- Only 3 — if everything is priority, nothing is
- Outcomes, not tasks ("Ship X" not "Work on X")
- Aligned to goals

**Prompt:**
```
Based on my goals, current projects, last week's outcomes, this week's calendar, and tasks.md — what should my top 3 priorities be this week?
```

**Then:** Update `tasks.md` with this week's top 3 as active items.

---

## Artifacts

- `tasks.md` updated with this week's items
