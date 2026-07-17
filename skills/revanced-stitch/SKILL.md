---
name: revanced-stitch
description: Generates a project DESIGN.md (semantic design contract) for handoff to design tools and coding agents. Captures atmosphere, color roles, type, components, layout, motion, responsive rules, and anti-patterns. Use when the user wants a DESIGN.md for Google Stitch, agent handoff, or revanced-frontend project contracts. Does not call external APIs by itself.
---

# Revanced Stitch — Design Contract Writer

> **Author:** chloevpin · **Inspired by:** taste-skill stitch / DESIGN.md handoff ideas — original wording  
> **Note:** This skill **writes files**. It does not run Google Stitch or any image API. Pair with those tools yourself if needed.

Goal: produce a **precise, opinionated `DESIGN.md`** that another agent or tool can implement without inventing a new aesthetic.

---

## 1. When to use

- User asks for a design system doc / DESIGN.md  
- Preparing handoff to Stitch or similar  
- Bootstrapping `revanced-frontend` project contract from a brief or existing UI  

---

## 2. Inputs to gather

From the user message, repo, or screenshots:

1. Product name and purpose  
2. Audience  
3. Vibe words / references  
4. Existing tokens (if any)  
5. Light/dark requirements  
6. Motion appetite  

If a critical input is missing, ask **one** question, then proceed with explicit assumptions listed in the doc.

---

## 3. Synthesis rules

### Atmosphere

Describe mood in prose. Encode axes in words:

- Density: gallery-airy · balanced · cockpit  
- Layout risk: symmetric · offset · experimental  
- Motion: static · fluid · cinematic  

### Color

For each token: **Name · Hex · Role**

Rules:

- One accent (saturation controlled)  
- Neutrals in one family (warm **or** cool)  
- No pure `#000` large fills; prefer off-black  
- No purple-neon default stack unless brand is actually purple  

### Typography

- Display, body, mono (if needed)  
- Hierarchy via weight/size/color — not only huge type  
- Body measure guidance (~65ch)  
- Note dashboard constraint: avoid decorative serif as UI face  

### Hero

- Asymmetry guidance when layout risk is mid/high  
- CTA count (prefer one primary)  
- Ban scroll lecture and version stickers unless product requires them  

### Components

Document buttons, cards, inputs, nav, loaders, empty/error — shape, fill, border, hover/active, focus.

### Layout

- Grid-first  
- Max width  
- Section rhythm  
- Mobile collapse rules (single column, 44px targets, no horizontal page scroll)  

### Motion

- What is allowed at the chosen budget  
- Spring vs CSS  
- Reduced motion required text  

### Anti-patterns

Explicit NEVER list tailored to this product (include global AI tells: 3 equal cards, Jane Doe, mesh purple, emoji icons, fake div product shots, em-dash chrome, etc.).

---

## 4. Output file format

Write `DESIGN.md` (project root unless user specifies a path) using this skeleton:

```markdown
# Design System: [Project Title]

## 1. Visual Theme & Atmosphere
…

## 2. Color Palette & Roles
- **Token Name** (#HEX) — role

## 3. Typography Rules
- **Display:** …
- **Body:** …
- **Mono:** …
- **Notes:** …

## 4. Component Stylings
- **Buttons:** …
- **Cards:** …
- **Inputs:** …
- **Nav:** …
- **Loaders / empty / error:** …

## 5. Layout Principles
…

## 6. Motion & Interaction
…

## 7. Responsive Rules
…

## 8. Anti-Patterns (Banned)
…

## 9. Implementation Notes for Agents
- Axes suggestion: LAYOUT_RISK=· MOTION_BUDGET=· INFO_DENSITY=·
- Stack preferences: …
- Assets: …
```

Be **specific** (hex, rem ranges, radius px). Vague DESIGN.md files are failed outputs.

---

## 5. Quality bar

- [ ] Every color has hex + role  
- [ ] Typefaces named (or explicit system stack with rationale)  
- [ ] Anti-patterns section is non-empty and concrete  
- [ ] Responsive rules included  
- [ ] Atmosphere matches the brief (not a generic “modern clean” paragraph)  
- [ ] Compatible with `contracts/DESIGN.template.md` spirit  

---

## 6. Handoff

After writing DESIGN.md, tell the user:

1. Path written  
2. Suggested axes for `revanced-frontend`  
3. That image/Stitch tools (if any) are **outside** this skill  

Do not pretend you generated Stitch frames unless a separate tool actually did.
