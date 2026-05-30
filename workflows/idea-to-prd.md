# Workflow: Product Idea → Project Brief → PRD

## Purpose
Take a raw product idea from concept to a fully drafted PRD in three structured steps, grounded in your team's context and project-specific research.

## When to Use
- You have a new product idea and need to formalize it
- A stakeholder has pitched something and you need to document it properly
- You're starting a new initiative and want to move fast without skipping rigor

## Trigger
Run `/idea-to-prd` in Claude Code.

---

## Steps

### Step 1: Load Context
Claude reads all files in:
- `context/` — company, team, goals, and recap
- The project folder you specify at runtime

### Step 2: Draft Project Brief
Claude drafts a project brief using `templates/project-brief.md`.
- You review and approve before moving forward
- You can ask Claude to revise any section

### Step 3: Draft PRD
Using the approved brief as input, Claude drafts a full PRD using `templates/ai_prd_template.md`.
- Sections are grounded in your context files
- You review and can request revisions

---

## Outputs
- `projects/[your-folder]/project-brief.md`
- `projects/[your-folder]/prd.md`

## Related Commands
- `/project-brief` — standalone brief drafting
- `/prd-review` — review a completed PRD with 5 personas
- `/humanize` — polish any output
