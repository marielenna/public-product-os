# Setup Checklist

Get up and running in ~30 minutes. Work through these steps in order.

---

## Step 1 — Clone the repo

```bash
gh repo clone marielenna/public-product-os
cd public-product-os
```

Or download the ZIP from GitHub and move it into your working directory.

---

## Step 2 — Open in Claude Code

```bash
claude .
```

This opens the repo as a Claude Code project. Claude will automatically read `CLAUDE.md` on every session.

---

## Step 3 — Fill in CLAUDE.md

Open `CLAUDE.md` and replace the placeholder sections with your own context:

- [ ] Your role and org
- [ ] What you're currently working on
- [ ] Any working style notes (optional but useful)

---

## Step 4 — Create your context files

Create a `context/` folder and add the following files. These ground the commands in your real work:

```
context/
├── company.md          ← What your org does, mission, key metrics
├── team_overview.md    ← Team roster, roles, key stakeholders
├── team_goals.md       ← Current quarter priorities and OKRs
├── year_recap.md       ← Prior year summary (helps with PRD context)
├── department_level_goals.md  ← Broader org goals
└── sprint_status.md    ← Active sprint status and blockers
```

You don't need all of these on day one. Start with `company.md` and `team_goals.md`.

---

## Step 5 — Connect MCPs

The commands work best when these are connected. Each has a dedicated setup guide in this folder.

### Granola (meeting notes)
- [ ] Install [Granola](https://granola.so) and let it record at least one meeting
- [ ] In Claude Code, authenticate the Granola MCP when prompted

### Superhuman Mail (email + calendar)
- [ ] Have a Superhuman account set up
- [ ] In Claude Code, authenticate the Superhuman MCP
- Used by: `/morning-brief`, `/eod-wrapup`

### Zapier → Jira (sprint tickets)
- [ ] Follow `zapier-setup-guide.md` to create your Zapier MCP server
- [ ] Add Jira actions and copy the MCP URL into Claude Code settings
- Used by: `/morning-brief`, `weekly-planning`

### Coda (documents)
- [ ] Follow `coda-mcp-setup-guide.md`
- Used by: `/morning-brief`

### Fullstory (product analytics)
- [ ] Authenticate the Fullstory MCP in Claude Code
- Used by: `weekly-planning`

> **None of these are required to start.** Commands skip unavailable sources and note it in the output.

---

## Step 6 — Try a command

Run your first command in Claude Code:

```
/morning-brief
```

If MCPs aren't connected yet, it will run from local files only (`tasks.md`, `context/`, `meetings/`). That's fine — you'll still get a useful output.

---


---

## You're done

Commands available:

| Command | What it does |
|---------|-------------|
| `/morning-brief` | Daily briefing from all connected sources |
| `/idea-to-prd` | Raw idea → project brief → full PRD |
| `/prd-review` | Multi-persona PRD review |
| `/prd-to-prototype` | PRD → interactive HTML prototype |
| `/eod-wrapup` | End-of-day open loops and action items |

For daily workflows, see `workflows/weekly-planning.md` and `workflows/quarterly-planning.md`.
