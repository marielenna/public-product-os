---
name: prd-to-prototype
description: >
  Takes a PRD and produces a branded interactive prototype. Prompts the user for the PRD
  path, reads the PRD to extract features and user flows, then builds a styled HTML prototype
  using your org's brand standards. Trigger this skill when the user wants to prototype or
  visualize a product from a PRD, or asks to turn a PRD into something interactive or visual.
---

# PRD → Prototype Skill

This skill reads a PRD and produces a branded HTML prototype based on its features, user journeys, and requirements.

## Step 1: Ask for the PRD

Before doing anything else, ask the user:

> "What is the path to your PRD? (e.g. `projects/[your-project]/prd.md`)"

Wait for their response. Then read the full PRD file they provide.

## Step 2: Extract from the PRD

From the PRD, identify:
- The product name and core purpose
- Key user personas and their goals
- Primary use cases and user journeys
- Core features (from the solution and requirements sections)
- Any UI or interaction notes

## Step 3: Load Brand Reference

Before writing any code, check if a brand reference file exists:

```
references/brand_guidelines.md
```

If it exists, read it in full. It should contain your org's color codes, typography rules, logo guidance, and design principles.

If no brand file exists, ask the user:

> "I don't see a brand guidelines file. What are your org's primary colors and any font preferences? Or should I use a clean neutral design?"

## Step 4: Apply Brand Rules

Use the brand guidelines loaded in Step 3. If none were provided, default to a clean, professional design:

```css
/* Default brand variables — replace with your org's values */
:root {
  --brand-primary: #1a1a1a;      /* Replace with your primary color */
  --brand-accent: #0066cc;       /* Replace with your accent color */
  --brand-background: #ffffff;
  --brand-text: #1a1a1a;
  --font-primary: 'Inter', 'Helvetica Neue', Arial, sans-serif;
}
```

Key design principles to apply regardless of brand:
- Strong visual hierarchy — clear headlines, readable body text
- Consistent spacing and alignment
- High contrast between text and backgrounds (WCAG AA minimum)
- Accent color for CTAs and interactive elements
- No decorative flourishes that distract from the content

## Step 5: Build the Prototype

Using what you extracted from the PRD and the brand rules above, build an HTML prototype that:
- Represents the core user journey from the PRD
- Includes the primary screens or states a user would encounter
- Uses real copy and labels drawn from the PRD (not placeholder lorem ipsum)
- Is interactive where possible (e.g. button clicks, tab navigation, simple form flows)

Deliver the prototype as a single self-contained HTML file.

## Step 6: Output Patterns by Format

### HTML / React Artifacts
```css
/* Brand CSS Variables — always include */
:root {
  --brand-primary: [YOUR PRIMARY COLOR];
  --brand-accent: [YOUR ACCENT COLOR];
  --brand-background: #ffffff;
  --brand-text: #1a1a1a;
  --font-primary: [YOUR FONT STACK];
}
```

- Background: white or primary brand color
- Headers/nav: primary brand color background with white or light text
- CTAs/buttons: accent color with high-contrast text
- Links: primary or accent color
- Avoid drop shadows unless legibility demands it

### PowerPoint / Presentations
- Title slides: primary brand color background, white text
- Content slides: white background, primary color headers, accent lines or section markers
- Data visualizations: use primary colors first, accent sparingly for multi-series charts

### Word Documents / Reports
- Header bar or top rule: primary or accent brand color
- Section headers: primary color, bold, title case
- Accent highlights: accent color background behind key callouts
- Body: dark text on white, clean sans-serif

## Quality Checklist

Before delivering any output, verify:
- [ ] Brand colors are present and consistent
- [ ] Typography is clean, readable, appropriate hierarchy
- [ ] Sufficient contrast (AA level minimum)
- [ ] No lorem ipsum — real copy from the PRD throughout
- [ ] Interactive elements are clearly distinguishable
- [ ] Design feels cohesive, not cobbled together
