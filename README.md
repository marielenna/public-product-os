# Public Product OS

A Claude Code–powered operating system for product managers at EdPlus. Slash commands, workflows, and tools you can drop into any PM repo and immediately put to work. This is catered to the tools used at EdPlus at ASU but can be changed for other organizations.

## What's Inside

### Commands (`.claude/commands/`)

| Command | What it does |
|---------|-------------|
| `/morning-brief` | Daily briefing from email, calendar, meetings, Jira, Coda, and Slack |
| `/idea-to-prd` | Turns a raw idea into a project brief, then a full PRD |
| `/prd-review` | Reviews your PRD through 5 personas (engineer, designer, user, exec, skeptic) |
| `/prd-to-prototype` | Converts a PRD into a branded interactive HTML prototype |
| `/eod-wrapup` | End-of-day summary — open loops, unanswered emails, action items |


### Workflows (`workflows/`)

- **`idea-to-prd.md`** — Full SOP for the idea → brief → PRD pipeline
- **`weekly-planning.md`** — Monday morning setup: review last week, check goals, set top 3
- **`quarterly-planning.md`** — End-of-quarter planning: reflect, gather inputs, draft and prioritize goals

---

## Quick Start

1. **[Clone this repo](https://github.com/marielenna/public-product-os)** into your working directory or copy what you need
2. **Fill in `CLAUDE.md`** with your role, org context, and working preferences
3. **Create `context/` files** — see the template in `CLAUDE.md` for what to include
4. **Run the setup checklist** — `tools/onboarding/setup-checklist.md`
5. **Try a command** — open Claude Code and run `/morning-brief` 

---

## MCP Integrations

These commands work best with the following MCPs connected:

| MCP | Used by |
|-----|---------|
| **Superhuman Mail** | `/morning-brief`, `/eod-wrapup`|
| **Granola** |  `/morning-brief` |
| **Zapier → Jira** | `/morning-brief`, `weekly-planning` |
| **Coda** | `/morning-brief` |
| **Fullstory** |`weekly-planning` |

Commands degrade gracefully if an MCP isn't connected — they'll skip that section and note it in the output.

---

## Customizing for Your Org

Most commands reference generic `context/` files. To make them yours:

1. Create `context/company.md` — org mission, product context, key metrics
2. Create `context/team_goals.md` — current priorities and OKRs
3. Create `context/team_overview.md` — team roster and stakeholders
4. Update `CLAUDE.md` — your role, working style, active projects

The commands will automatically use these files to ground their output in your context.

---

## Built with

- [Claude Code](https://claude.ai/code) — Anthropic's CLI for Claude
- [Granola](https://granola.so) — AI meeting notes
- [Superhuman](https://superhuman.com) — Email client
- [Coda](https://coda.io) — Docs and databases
- Zapier MCP — Jira + Slack integrations
- [Fullstory](https://help.fullstory.com/hc/en-us/articles/39130808411031-Fullstory-MCP) — Product analytics
