# CLAUDE.md

## Who I Am

<!-- Fill this in with your role and context. Claude reads this automatically. -->

I'm a [your title] at [your org] working on [what you build].

<!-- Optional: add a working style guide so Claude adapts to how you communicate -->
<!-- Example: I prefer async over meetings, data-driven decisions, and concise writing. -->

## The Company

<!-- Brief context about your org. Or point to a context file: -->

See `context/company.md` for details.

## Current Focus

<!-- What you're working on right now. Or point to a context file: -->

See `context/team_goals.md` for current priorities.

## How I Work

- Writing style: See `templates/writing-style.md`
- Document formats: See `templates/`

## Key Commands

- `/prd-review` — Multi-perspective PRD review
- `/idea-to-prd` — Take an idea all the way to a PRD
- `/morning-brief` — Daily briefing from all connected sources
- `/eod-wrapup` — End-of-day summary of open loops and unanswered emails
- `/prd-to-prototype` — Turn a PRD into an interactive HTML prototype

## Folder Structure

```
context/      → Company, product, team, goals (you populate these)
workflows/    → Multi-step SOPs
tools/        → Utility scripts and setup guides
projects/     → Active projects (create subfolders per project)
meetings/     → Notes by type
  1-on-1s/   → Organized by Month Year folders
tasks.md      → Weekly task tracking
```

## Context Files to Create

To get the most out of these commands, create the following files and fill them in:

```
context/
├── company.md          → What your org does, mission, key metrics
├── team_overview.md    → Team roster, roles, stakeholders
├── team_goals.md       → Current quarter goals and priorities
├── year_recap.md       → Prior year summary (for PRD context)
├── department_level_goals.md → Broader org goals
└── sprint_status.md    → Active sprint status and blockers
```


## Setup

See `tools/onboarding/` for step-by-step guides:
- `setup-checklist.md` — Start here
- `claude-project-instructions.md` — Configuring Claude Code for this repo
- `coda-mcp-setup-guide.md` — Connecting Coda MCP
- `zapier-setup-guide.md` — Connecting Zapier (for Jira, Slack)
- `daily-workflow-prompts.md` — Sample prompts to get started
