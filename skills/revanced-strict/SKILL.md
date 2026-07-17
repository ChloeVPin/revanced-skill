---
name: revanced-strict
description: High-pressure frontend rails for models that under-vary layout and over-wrap headlines. Forces a written design plan, AIDA page flow, hard hero line limits, gapless feature grids, stronger motion discipline, and aggressive anti-slop bans. Use when default revanced-frontend still looks safe or template-like (especially GPT/Codex-class runs).
---

# Revanced Strict — High-Pressure Frontend Rails

> **Author:** chloevpin · **Inspired by:** stricter taste variants (e.g. gpt-taste) — original rules  
> Use **instead of or on top of** `revanced-frontend` when outputs look too safe, too centered, or too samey.

This skill assumes the model will try to **collapse** to a familiar template. Your job is to **break the collapse** with a plan, hard constraints, and a pre-flight you cannot skip.

---

## 0. Mandatory design plan (before code)

Output a `<design_plan>` block first:

```xml
<design_plan>
  <read>one-line design read</read>
  <axes>LAYOUT_RISK · MOTION_BUDGET · INFO_DENSITY</axes>
  <layout_seed>how you broke the default (see §1)</layout_seed>
  <type>display + body pair and why</type>
  <accent>single accent + neutrals</accent>
  <page_flow>AIDA section list</page_flow>
  <motion>what actually moves (or "static")</motion>
  <risks>what could still look like slop</risks>
</design_plan>
```

No code until this exists.

---

## 1. Break the loop (layout variance)

Models repeat left-text/right-image, then invert once, then give up.

Before building, pick a **layout seed** using a real source of entropy available in the environment:

- Hash of the product name → pick from a table, **or**
- Run a tiny script / mental modulo if tools allow, **or**
- Use the user’s reference brand as the seed  

| seed % 6 | Opening layout |
|---:|---|
| 0 | Split 45/55 media-left |
| 1 | Split 40/60 type-left, media bleeding edge |
| 2 | Typographic hero, media as second band only |
| 3 | Asymmetric 2-col with overlapping margin offset (desktop only) |
| 4 | Horizontal product strip under compact hero  
| 5 | Editorial single column with large pull-figure mid-hero |

**Mobile:** all of the above collapse to one column with consistent padding. No horizontal page scroll.

State the chosen seed in the plan. Do **not** default to centered stacked hero + 3 cards unless LAYOUT_RISK ≤ 3.

---

## 2. AIDA page flow + spacing

Structure marketing pages as:

1. **Attention** — hero with clear promise  
2. **Interest** — proof / mechanism / product truth  
3. **Desire** — benefits, social proof, concrete outcomes  
4. **Action** — final CTA band  

Section vertical rhythm: **generous**. Prefer large band gaps (think `clamp(4rem, 10vw, 8rem)` class spacing) over cramped “card soup.”

Avoid repeating the same section chrome (identical eyebrow + H2 + 3 cards) more than once.

---

## 3. Hero iron rules

- Display headline: **maximum 2 lines on desktop** at the chosen type size.  
- If it wraps to 3+, **shorten copy** or widen measure — do not shrink the whole hero into a narrow column that forces 5–6 line posters.  
- Subcopy: short, concrete, no slogan fog.  
- **One** primary CTA in the hero. Secondary text link only if needed.  
- No scroll lecture, no fake version pill, no weather strip.  
- CTA contrast must pass; no low-contrast ghost-on-ghost buttons.

---

## 4. Gapless feature grids

If you use a bento / feature mosaic:

- Every cell has real content; **no empty decorative cells**  
- Gaps are intentional and even; no “missing tile” holes  
- Prefer 2+1, 1+2, or 4-cell asymmetric over three equal columns  
- Labels live in a clear hierarchy (title → body → optional meta), not floating micro-junk  

---

## 5. Motion discipline

When MOTION_BUDGET ≥ 6:

- Prefer one strong scroll pattern (pin stack **or** horizontal pan **or** staggered reveal) — not all three half-done  
- Hover: opacity/transform only; optional magnetic translate **outside** React render thrash (motion values, not `useState` per mouse pixel)  
- Always support `prefers-reduced-motion`  
- Forbidden: `window.onscroll` → `setState` loops; animating width/height/top/left for effects  

When MOTION_BUDGET ≤ 4: static + hover only. Do not fake “cinematic.”

---

## 6. Component pressure

Ship at least **two** non-default interactions when budget allows, chosen for the product (examples — pick what fits, do not dump all):

- Shared-element / layout transition between states  
- Inline micro-visual in the headline area (small image or product glyph — not emoji)  
- Sticky product frame while copy scrolls (only if implemented cleanly)  
- Marquee of **real** customer marks (SVG), not word-list fluff  

---

## 7. Content & asset bans (strict mode)

- No em-dash / en-dash in UI strings  
- No “QUESTION 05”, “SECTION 01”, “0.1 / OVERVIEW” eyebrows  
- No Jane Doe, Acme, Nexus, SmartFlow  
- No `99.99%` / empty `10x` claims without context  
- No Elevate / Unleash / Seamless / Next-Gen  
- No emoji icons  
- No fake div dashboards  
- No invisible or ultra-low-contrast button labels  

---

## 8. Pre-flight (all must pass)

```text
### Strict pre-flight
- [ ] <design_plan> emitted before code
- [ ] Layout seed chosen and not boring-default (unless risk ≤ 3)
- [ ] Hero headline ≤ 2 lines desktop
- [ ] AIDA flow present
- [ ] No 3-equal-card default as sole features band
- [ ] Single accent; coherent neutrals
- [ ] CTA contrast OK
- [ ] Motion matches budget (or explicitly static)
- [ ] No strict-mode content bans violated
- [ ] Revanced receipt printed (see revanced-frontend)
```

If any box fails, fix before delivery.
