# Idea → Project Brief → PRD Workflow

## Step 1: Get Project Folder

Before starting, ask the user:

> "What is the path to your project folder? (e.g. `projects/[your-project]`)"
>
> If the folder doesn't exist yet, ask if they'd like to create it.

Wait for their response before continuing.

---

## Step 2: Load Context

Read all of the following files in full:

**Company & Team Context:**
- `context/company.md`
- `context/team_overview.md`
- `context/team_goals.md`
- `context/year_recap.md`

**Project Context:**
Read all files found in the project folder the user specified. If the folder is empty or doesn't exist, note that and continue.

Confirm to the user: "I've loaded your context and project folder. Ready to start."

---

## Step 3: Capture the Idea

Ask the user:

> "Describe your product idea. It can be rough — a sentence, a problem you heard, a meeting takeaway. Whatever you have."

Wait for their response.

---

## Step 4: Draft Project Brief

Using the user's idea and all loaded context, draft a project brief following the structure in `templates/project-brief.md`:

- Background (tie to team goals where relevant)
- Problem Statements (use the "I am / trying to / but / because / feel" format)
- Goals and Non-Goals
- Hypothesis
- Vision Narrative
- Rough Scoping & Timeline
- Key Trade-offs & Decisions
- Open Questions

Apply the writing style from `templates/writing-style.md`.

After drafting, present the brief to the user and ask:

> "Here's your project brief. Would you like to revise anything, or are you ready to move on to the PRD?"

Wait for their response. Revise if needed. Do not proceed until the user approves.

---

## Step 5: Draft PRD

Using the approved project brief as the foundation, draft a full PRD following the structure in `templates/ai_prd_template.md`. Use context files to fill in relevant market, stakeholder, and strategic details.

Key sections to complete:
- About
- Market Insights (use company context and team goals)
- Customer Segments & User Personas
- The Problem (Use Cases, Pain Points, Problem Statement, Hypotheses)
- The Solution (Ideation, Leveraging AI, Feature Prioritization, Roadmap)
- Requirements (Functional, Non-functional, AI & Data)
- Risks
- Positioning
- Measuring Success

Apply the writing style from `templates/writing-style.md`.

After drafting, present the PRD to the user and ask:

> "Here's your PRD draft. Want to revise any sections, or is it ready to save?"

---

## Step 6: Save Outputs

Once the user approves, save the documents:

- Project Brief → `[project-folder]/project-brief.md`
- PRD → `[project-folder]/prd.md`

Confirm to the user: "Saved. Run `/prd-review` anytime to get a multi-persona review of your PRD."
