---
name: revanced-frontend
description: Strict frontend rails for AI coding agents. Concept-first craft for landings and product marketing sites. Forces a one-line concept, owned visual system, conversion jobs in order, signature moment when ambition is high, anti-slop defenses, and a review receipt. Use for landings, portfolios, marketing pages, and light redesigns. Inspired by taste-skill; original ruleset by chloevpin.
---

# Revanced Frontend — Strict Frontend Rails

> **Tagline:** Strict frontend rails for AI agents  
> **Author:** chloevpin  
> **Inspired by:** [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) — original wording, not a fork.

Landings, portfolios, marketing sites, controlled redesigns.  
Not default scope: dense admin dashboards, spreadsheet products, multi-step app wizards, native shells (unless user expands).

Every rule is **contextual**. Read the brief. Pull only what fits.

---

## 0. Intent lock

You ship interfaces that look **decided and engineered** — not generated, not template SaaS, not “award” theater without craft.

**Two excellence bars (pick one deliberately):**

| Bar | When | What excellence means |
|---|---|---|
| **Craft product** | B2B SaaS, tools, docs marketing | Clarity, product is the demo, tiny owned system, functional motion, trust. Think Linear / Stripe / Raycast / Vercel class. |
| **Award experience** | Brand, portfolio, campaign, product launch with budget | Same craft floor **plus** one signature moment, scroll narrative, real media, choreographed time. Awwwards-adjacent. |

Most agent tasks are **craft product**. Do not fake WebGL spectacle when the job is a clear product story.

**Non-negotiables on both bars:**

1. One written **concept** before code  
2. Owned visual system (not zinc-emerald default)  
3. Visitor questions answered in order  
4. Usability (contrast, mobile, performance) never sacrificed for decoration  
5. Review receipt at the end  

---

## 1. Concept first (mandatory)

Before markup, output:

```text
CONCEPT: <one sentence — the site's single idea>
BAR: craft-product | award-experience
SIGNATURE: <one memorable moment, or "none — craft restraint">
SYSTEM: type pair · 2–3 colors · radius · motion language
```

Examples:

- `CONCEPT: The finish package is the meeting — open a living register and watch marks resolve.`  
- `CONCEPT: Speed as identity — black field, one electric accent, motion that never idles.`  

If you cannot state a concept, you will build a section checklist. That is failure.

**One signature moment max** on award-experience. Zero or one on craft-product (often the product demo itself is the moment).

---

## 2. Design read

State one line:

> **Reading this as:** `<page kind>` for `<audience>`, language `<vibe>`, foundation `<system or aesthetic>`.

Extract: page kind, vibe words, references, audience, existing brand, hard constraints (a11y, regulated, low-motion).

If ambiguous: **one** question max. Prefer inference.

### Anti-defaults

Do not auto-pick: purple mesh, centered dark blob hero, three equal feature cards, Inter + slate, glass everywhere, infinite floats, div-only fake product chrome as the whole design, zinc + emerald + pill CTAs as “safe SaaS.”

---

## 3. Project contract wins

Load `DESIGN.md` / `docs/DESIGN.md` / `contracts/DESIGN.md` when present. Contract overrides skill defaults. User message overrides contract for that turn (note conflict in receipt).

---

## 4. Axes

| Axis | Low (1–3) | Mid (4–7) | High (8–10) |
|---|---|---|---|
| **LAYOUT_RISK** | Symmetric | Offset | Experimental |
| **MOTION_BUDGET** | Static + hover | CSS / light reveal | Scroll choreography |
| **INFO_DENSITY** | Gallery air | Normal marketing | Packed |

**Marketing default:** `6 / 4 / 3`.  
Craft-product rarely needs density above 4. Award-experience motion can rise; density still stays disciplined.

Presets (override in chat):

| Use case | L | M | D |
|---|---:|---:|---:|
| Calm SaaS | 5 | 4 | 3 |
| Craft product (Linear-class) | 5 | 5 | 3 |
| Agency / experimental | 9 | 8 | 3 |
| Portfolio | 8 | 6 | 3 |
| Trust / public-sector | 3 | 2 | 4 |

---

## 5. Foundation

### Real design systems

If brief maps to Material, Fluent, Carbon, Polaris, Primer, GOV.UK, USWDS, etc. — install **official** packages. One system per tree. shadcn allowed only **customized**, never stock theme.

### Aesthetics

Glass, bento, brutalist, editorial, dark-tech — build honestly; label platform approximations (e.g. liquid glass).

---

## 6. Craft product bar (default for SaaS)

Study patterns from elite product marketing (Linear, Stripe, Vercel, Raycast class) — **principles**, not clones:

1. **Product is the demo** — hero shows real product motion or a high-fidelity capture of the product doing the job, not a generic illustration grid.  
2. **POV in the headline** — how it feels / the job done, not a feature laundry list.  
3. **Restraint below the fold** — fewer sections, each inevitable. No testimonial wall + logo soup + six feature bands by default.  
4. **Uniform components** when listing many items (Raycast pattern): one card language, generous space, single illustration system.  
5. **Functional motion only** — load, hover, subtle product loops. Motion that does not explain is cut.  
6. **Copy clarity beats decoration** — every line earns its place.  
7. **Trust is earned** — logos or one hard result, not both over-packaged.  

If the page could be any AI notes app with a logo swap, you failed ownership **and** craft.

---

## 7. Award experience bar (only when ambition matches)

Informed by Awwwards (Design 40% · Usability 30% · Creativity 20% · Content 10%) and recent SOTD patterns:

### 7.1 What winners share

- **One signature moment** you remember after leaving  
- **Scroll as narrative** (time is designed; GSAP/ScrollTrigger-class control when motion is high)  
- **Tiny system pushed hard** — 1–2 typefaces, 2–3 colors (e.g. black + one electric accent)  
- **Huge type scale swings** — display vs meta  
- **Real media** — film, photo, 3D, custom illustration  
- **Choreography** — loader / transitions / stagger as one language  
- **Performance under complexity** — aim 60fps; usability is 30% of award score  
- **Mobile designed**, not bolted on  
- **Concept** — form expresses subject  

### 7.2 What fails awards (and fails craft)

- Template / AI-builder / “section checklist” DNA  
- Mobile afterthought  
- Slow load, janky scroll  
- No memorable moment **or** twenty forgettable effects  
- Placeholder content and stock filler  
- Creativity that breaks navigation  

### 7.3 Signature moment rules

- Exactly **one** primary idea (scroll-scrubbed story, pin stack, mask reveal, spatial product metaphor, kinetic type identity).  
- Everything else supports it.  
- If MOTION_BUDGET &lt; 5, signature must work as a **static composition** first; motion is enhancement.

### 7.4 Realistic ambition

Do not claim SOTD quality without real media, motion investment, and polish time.  
Agent output should still **aim at the method**: concept, system, signature, usability.

---

## 8. Conversion jobs (both bars)

A B2B or product page answers, **in order**:

1. What is this?  
2. Is it for me?  
3. How does it work?  
4. Why believe you?  
5. What do I do next?  

**Jobs, not skins.** Same jobs can look entirely different. Cloning another site’s palette, pill buttons, and 01/02/03 columns is failure even if the jobs are correct.

### Section jobs (implement with original form)

| Job | Notes |
|---|---|
| Nav + one primary action | Quiet chrome |
| Promise + how (product near claim) | Two-zone first view preferred for software |
| Trust | After promise; light packaging |
| Mechanism | 1–2 evidence blocks, not six |
| Full lifecycle if workflow product | Complete the loop (capture → review → close) |
| Belief | One quote **or** one hard result |
| Next action | Same primary button language |

### Hero (software)

- Prefer **copy + product** in first view.  
- No third competing cluster (floating metric tiles stealing the H1).  
- Product UI must prove the **headline claim** (states, comments, outcomes).  
- H1 ≤ ~2 lines; short sub; one solid primary CTA.  
- Hero text stack: optional label · H1 · sub · CTAs only.

### Scannable headings

Read only H1/H2 top to bottom — they must form a complete sales argument.

### Cognitive restraint

- Prefer **fewer sections that each do one job**.  
- Under-design secondary material.  
- Marketing chrome quieter than product / signature.  
- Whitespace separates jobs; it is not empty decoration for its own sake.  
- **When in doubt, cut.**

---

## 9. Visual system (owned)

### Type

- 1–2 families max.  
- Display can be expressive; UI/body stay readable (≥16px body on marketing).  
- Hierarchy via scale, weight, color — not only huge type.  
- Serif as primary UI face for dashboards: avoid.

### Color

- **2–3 colors** in the system (bg, ink, one accent) unless brand requires more.  
- One accent for CTAs/focus/state.  
- Surface ladder: canvas → raised → inset → inverse when needed — not one flat wash.  
- **Contrast non-negotiable:** never light text on light surfaces; never fight a light CSS class with `text-white`.

### Shape

- One radius language (sharp tool vs soft product). Document exceptions.

### Anti-convergence

Rotate type, accent family, opening layout, surface material across projects.  
Zinc + emerald + full pills is a known convergence trap — ban as default.

---

## 10. Motion

| Budget | Allowed |
|---:|---|
| 1–3 | Hover/active only |
| 4–6 | CSS transitions; light in-view |
| 7–10 | Scroll choreography (prefer one library story: Motion or GSAP) |

- Animate transform/opacity; no layout thrash.  
- `prefers-reduced-motion` mandatory when budget &gt; 3.  
- No `window.onscroll` → React state loops.  
- **Claimed motion must exist.** Else drop the dial.  
- Prefer **one** strong scroll pattern over five weak fades.

---

## 11. Media

Priority:

1. Generated or real photography / product capture  
2. High-fidelity product UI that is actually the product  
3. Never: empty gray box theater as the only visual craft  

Award-experience requires real media. Craft-product requires product truth.

---

## 12. Stack defaults

- Prefer existing framework.  
- Check `package.json` before new deps; print install commands.  
- Tailwind: match v3/v4.  
- Icons: Phosphor / Radix / Tabler / Hugeicons; no emoji icons.  
- Full viewport: `min-h-[100dvh]` not bare `h-screen`.  
- Grid over flex percentage math.

---

## 13. Slop defenses (ban by default)

### Visual

Neon outer glows · mesh purple blobs · rainbow accents · gradient headline habit · custom cursors · glass on everything · hand-rolled decorative SVG filler · div-only fake dashboards as hero art  

### Type / chrome

Em/en dashes in UI copy · section-number eyebrows spam · hero BETA stickers · scroll lectures · weather strips · mono decoration strips · pills on photos · fake film credits · version footers on marketing  

### Layout / content

Three equal feature cards as default · always-centered hero when risk &gt; 4 · Jane Doe / Acme / 99.99% / Elevate-Unleash copy · quiet-used-by clichés · stale mono pamphlet · cramped marketing density · directory-card “logos” · three-cluster hero · incomplete lifecycle · new scene every section · max-volume brand · **reference twin** of known demos · **section checklist design** with no concept · **slop accumulation** (grid + monograms + dual theaters + metrics + timeline + dark panels at once) · **invisible text** (light-on-light)  

### Motion / eng

Scroll listeners thrashing React · animating top/left/width/height · motion claimed but missing · reduced-motion ignored  

---

## 14. Redesign modes

| Mode | Behavior |
|---|---|
| Greenfield | Full rails |
| Touch-up | Structure kept; hierarchy/spacing/type/color/states |
| Overhaul | New system; silent contracts hold |

**Never change silently:** URLs, nav labels, form names/ids, legal/pricing copy, wordmark geometry, CI testids.

Fix order: hierarchy → spacing → type → color → states → motion → polish.

---

## 15. Performance and a11y floor

- Transform/opacity animation  
- Reduced motion  
- Visible focus  
- WCAG AA contrast  
- Meaningful alt  
- Z-index only for systemic layers  
- Aim: no layout shift from late images; 60fps if animating  

---

## 16. Review receipt (mandatory)

```text
### Revanced receipt
- CONCEPT: …
- BAR: craft-product | award-experience
- SIGNATURE: … | none
- Design read: …
- DESIGN.md: yes/no (path)
- Axes: LAYOUT_RISK=· MOTION_BUDGET=· INFO_DENSITY=·
- SYSTEM: type · colors · radius · motion
- Jobs order: what → for me → how → believe → next
- Pre-ship:
  - [ ] Concept stated before code
  - [ ] Owned system (not convergence palette)
  - [ ] Product proves headline (if software)
  - [ ] No three-cluster hero
  - [ ] Lifecycle complete if claimed
  - [ ] H1/H2 chain scannable
  - [ ] Section count justified (cut overbuild)
  - [ ] Contrast OK (no light-on-light / class fights)
  - [ ] Motion matches budget
  - [ ] Signature is one idea (or none)
  - [ ] Mobile readable
  - [ ] Reduced motion considered
  - [ ] Silent contracts (if redesign)
  - [ ] Receipt not in customer UI chrome
- Risks: …
```

---

## 17. Quick start

1. CONCEPT + BAR + SIGNATURE + SYSTEM  
2. Design read  
3. Load DESIGN.md  
4. Set axes  
5. Implement jobs with owned form  
6. Run slop defenses  
7. Print receipt  

Pair with **`revanced-complete`** for full files.  
Pair with **`revanced-strict`** when models collapse to safe templates.  
Pair with **`revanced-redesign`** for existing codebases.

---

## 18. Research anchors (for agents)

- Awwwards weights: Design 40 · Usability 30 · Creativity 20 · Content 10  
- Winners: one signature moment, scroll narrative, tiny system, real media, performance  
- Craft product: product-is-demo, restraint, functional motion (Linear/Stripe/Raycast/Vercel class)  
- Losers: templates, AI-default layouts, mobile afterthoughts, no concept  

Do not imitate a specific winner’s skin. Imitate **method**.
