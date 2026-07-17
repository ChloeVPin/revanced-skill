---
name: revanced-redesign
description: Audit-first redesign skill for existing sites and apps. Scans the codebase, lists design failures, then upgrades type, color, layout, motion, and states without breaking routes, forms, or brand locks. Use when improving an existing project rather than greenfield.
---

# Revanced Redesign — Audit First, Then Upgrade

> **Author:** chloevpin · **Inspired by:** Leonxlnx/taste-skill redesign patterns (original wording)  
> Pair with `revanced-frontend` for construction rails and receipt format.

You are improving something that already ships. **Do not rewrite the product from scratch** unless the user explicitly asks for a full visual overhaul and accepts migration cost.

---

## 0. Mode detection (first)

| Mode | Signals | Behavior |
|---|---|---|
| **Touch-up** | “polish”, “make it less AI”, small scope | Keep structure; fix hierarchy, spacing, type, color, states |
| **Targeted evolution** | Specific pages/components named | Audit only those surfaces; match surrounding system |
| **Overhaul** | “new brand”, “full redesign”, new tokens allowed | New visual system, but **silent contracts still hold** |

State the mode in one line before editing.

---

## 1. Sequence (never skip)

1. **Scan** — Framework, styling system (Tailwind v3/v4, CSS modules, etc.), component library, existing tokens, routes.  
2. **Diagnose** — Run the audit below. Produce a written issue list with severity.  
3. **Plan** — Fix order (see §3). Call out what will *not* change.  
4. **Patch** — Smallest diffs that move quality. Prefer tokens and shared components over one-off magic.  
5. **Receipt** — Print redesign receipt (end of file).

---

## 2. Design audit checklist

Mark each item: **OK** · **Fix** · **N/A**

### Typography

- [ ] Default/system or Inter-only stack for a brand surface  
- [ ] Headlines weak (scale only via size; no tracking/weight plan)  
- [ ] Body lines too long (> ~75ch) or too tight leading  
- [ ] Only 400/700 weights; no mid weights for hierarchy  
- [ ] Data numbers not tabular / mono where alignment matters  
- [ ] Orphans / ugly wraps (no `text-wrap: balance` / `pretty` where supported)  
- [ ] All-caps micro-labels overused  

### Color & surfaces

- [ ] Pure `#000` / pure `#fff` large fields with no depth  
- [ ] Multiple competing accents  
- [ ] Warm and cool grays mixed randomly  
- [ ] Purple/blue mesh “AI gradient” default  
- [ ] Untinted pure-black shadows  
- [ ] Mid-page unexplained light↔dark section flips  
- [ ] Flat sterile panels with zero material language (when brand wants depth)  

### Layout

- [ ] Three equal feature cards as the only features pattern  
- [ ] Every section the same centered column recipe  
- [ ] Flex `%` + `calc` hacks instead of grid  
- [ ] Inconsistent max-width / section padding scale  
- [ ] `h-screen` heroes causing mobile jump (prefer `dvh` patterns)  
- [ ] Horizontal overflow on small viewports  

### Interaction & states

- [ ] Buttons with no hover/active/focus  
- [ ] Missing loading / empty / error for interactive views  
- [ ] Focus rings removed without replacement  
- [ ] Dead click targets < ~44px on mobile  

### Content

- [ ] Jane Doe / Acme / 99.99% / “Elevate your workflow” sludge  
- [ ] Em-dash decoration spam in UI copy  
- [ ] Scroll lecture cues, fake BETA stickers, weather strips  

### Components & icons

- [ ] Stock shadcn/default kit look with no brand pass  
- [ ] Emoji as icons  
- [ ] Fake product UI from empty nested boxes  
- [ ] Inconsistent icon stroke set  

### Code hygiene (design-adjacent)

- [ ] Magic spacing values with no scale  
- [ ] Duplicate one-off color hexes instead of tokens  
- [ ] Unreachable CSS / dead theme classes  

### Strategic omissions (usually missing)

- [ ] Prefer-reduced-motion handling  
- [ ] Dark mode parity (if product claims dual theme)  
- [ ] Consistent form label/error placement  
- [ ] Skeleton loaders that match final layout  

---

## 3. Fix priority

Apply in this order unless the user re-prioritizes:

1. **Hierarchy** — type scale, weight, color roles  
2. **Spacing rhythm** — section and component spacing scale  
3. **Color system** — one accent, coherent neutrals  
4. **Layout structure** — grid, alignment, section variety  
5. **States & a11y** — focus, loading, empty, error  
6. **Motion** — only after structure is solid  
7. **Polish** — borders, shadows, micro-details  

Do not start with animation on a broken hierarchy.

---

## 4. Upgrade techniques (stack-agnostic)

### Type

- Introduce a deliberate display + body pair that fits the brand (from existing fonts when possible).  
- Tighten tracking on large display; open tracking on tiny labels carefully.  
- Cap reading measure; raise body leading into a readable band.  

### Layout

- Replace equal card trinities with zigzag, 2+1 grids, or media-led rows when it fits content.  
- Unify container width and section vertical rhythm.  
- Collapse multi-column cleanly below tablet breakpoints.  

### Surfaces

- Tint shadows toward surface hue.  
- Prefer one radius system.  
- Use cards only when elevation encodes hierarchy; otherwise dividers/space.  

### Motion

- Prefer CSS/transform opacity.  
- Remove gratuitous loops on marketing chrome.  
- Respect reduced motion.  

---

## 5. Silent contracts (never change without explicit ask)

- Public URL paths and anchors  
- Navigation labels users already know  
- Form field `name` / `id` / validation API shapes  
- Legal, pricing, and compliance copy (unless asked to rewrite)  
- Logo / wordmark geometry  
- Analytics IDs, `data-testid` used in CI (unless asked)  

If a visual change requires a copy change, **ask** or flag it in the receipt.

---

## 6. Working with the existing stack

- Keep Tailwind/CSS-in-JS/etc. already in the repo.  
- Match major versions (do not “upgrade Tailwind” casually mid-redesign).  
- Prefer editing shared tokens (`globals.css`, theme files) over fifty local one-offs.  
- Check `package.json` before adding libraries.  

---

## 7. Redesign receipt (mandatory)

```text
### Revanced redesign receipt
- Mode: touch-up | targeted | overhaul
- Stack found: …
- Issues found (top 5–10): …
- Changes applied: …
- Intentionally unchanged (silent contracts): …
- Axes if used (LAYOUT_RISK / MOTION_BUDGET / INFO_DENSITY): …
- Residual risks: …
```

---

## 8. Anti-patterns for redesign agents

- Full-folder rewrites “for cleanliness” without need  
- Renaming routes while “just polishing UI”  
- Swapping the design system mid-task without agreement  
- Applying a global aesthetic pack that fights existing brand tokens  
- Shipping motion before type/spacing are fixed  

When in doubt: **smaller diff, clearer audit, honest receipt.**
