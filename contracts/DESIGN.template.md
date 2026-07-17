# Design Contract

> Copy this file to the project root as `DESIGN.md` (or keep it under `docs/DESIGN.md`).
> When present, **revanced-frontend treats this file as higher priority than skill defaults.**

## Product

- **Name:**
- **One-line purpose:**
- **Primary audience:**
- **Tone:** (e.g. calm B2B · playful consumer · editorial · industrial)

## Surfaces in scope

- Landing / marketing:
- App / product UI:
- Docs:
- Other:

## Visual system

### Color

- Background:
- Surface / card:
- Text primary:
- Text muted:
- **Single accent** (hex + usage rule):
- Borders / dividers:
- Dark mode strategy: (class · media · dual tokens · none)

### Typography

- Display / headlines:
- Body:
- Mono (if any):
- Scale notes (e.g. hero max lines, body max measure):

### Shape & elevation

- Radius system: (sharp · soft · pill — pick one primary)
- Shadow style: (none · hairline · soft diffusion)
- Border style:

### Layout

- Max content width:
- Section vertical rhythm:
- Grid preference: (12-col · bento · editorial asymmetric · app chrome)
- Mobile collapse rules:

### Motion

- Default motion budget (1–10):
- Allowed libraries: (CSS only · Motion · GSAP · none)
- Reduced motion: always honor `prefers-reduced-motion`

## Brand assets

- Logo path / rules:
- Photography style:
- Icon set: (Phosphor · Radix · Tabler · other — avoid hand-rolled decorative SVG by default)

## Explicit bans for this project

List project-specific do-nots (on top of global anti-slop rails):

-
-
-

## Approved examples

- Good reference URLs or internal paths:
- Anti-examples (looks we refuse):

## Never change silently (redesigns)

- URL structure
- Nav labels users know
- Form field names / IDs
- Legal copy
- Brand wordmark geometry (unless redesign is explicit)

## Review receipt expectations

Agents using revanced-frontend should print a short receipt covering:

1. Design read (one line)
2. Axes used (LAYOUT_RISK / MOTION_BUDGET / INFO_DENSITY)
3. Whether this contract was loaded
4. Pre-ship checklist pass/fail
