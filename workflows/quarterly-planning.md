# Quarterly Planning Workflow

Run this in the last 2 weeks of each quarter to plan the next.

## Overview

| Phase | Time | Output |
|-------|------|--------|
| 1. Reflect on quarter | 2 hrs | Quarter review doc |
| 2. Gather inputs | 3 hrs | Stakeholder needs |
| 3. Draft goals | 2 hrs | Goal candidates |
| 4. Prioritize | 2 hrs | Final goals |
| 5. Align & commit | 2 hrs | Published plan |

**Total:** ~2 days spread across 2 weeks

---

## Phase 1: Reflect on Current Quarter

**Questions:**
- Did we hit our goals? Why/why not?
- What surprised us?
- What would we do differently?
- What capabilities did we build?

**Prompt:**
```
Review our Q[X] goals in `context/team_goals.md`. For each goal, assess: did we hit it, what drove the outcome, what did we learn?
```

**Output:** Quarter retrospective doc

---

## Phase 2: Gather Inputs

### From Customers
- Top feature requests
- Biggest pain points
- Churn reasons

### From Engineering
- Technical debt priorities
- Platform investments needed
- Capacity constraints

### From Executives
- Company priorities
- Strategic bets
- Resource changes

**Prompt:**
```
Synthesize feedback from [paste notes] into themes. What are the top 5 things we're hearing?
```

---

## Phase 3: Draft Goals

**For each potential goal:**
- **Metric:** How will we measure it?
- **Target:** What's success?
- **Why now:** Why this quarter?
- **Initiatives:** What work gets us there?
- **Dependencies:** What do we need?

**Framework:**
- 3-5 goals per quarter
- Mix of:
  - Business outcomes (revenue, adoption)
  - Product outcomes (features, quality)
  - Foundation (tech debt, capabilities)

**Prompt:**
```
Based on the inputs gathered, draft 5 candidate goals for Q[X+1]. For each, include metric, target, rationale, and key initiatives.
```

---

## Phase 4: Prioritize

**Prioritization criteria:**
1. Impact on company goals
2. Customer value
3. Feasibility given resources
4. Dependencies and risk

**Exercise:**
- Stack rank all candidates
- Check capacity against top choices
- Identify what you're NOT doing

**Prompt:**
```
Help me prioritize these goal candidates. Consider impact, feasibility, and dependencies. What should our top 3-4 be?
```

---

## Phase 5: Align & Commit

**Alignment meetings:**
- Review with manager
- Sync with eng/design leads
- Present to stakeholders

**Final goal doc includes:**
- Goals with metrics and targets
- Key initiatives per goal
- Dependencies and risks
- What we're NOT doing
- Review cadence

**Prompt:**
```
Format our Q[X+1] goals using the `templates/one-pager.md` template. Make it ready for stakeholder review.
```

---

## Artifacts

- Quarter retrospective
- Q+1 goals doc (update `context/team_goals.md`)
- Stakeholder presentation
- Team communication
