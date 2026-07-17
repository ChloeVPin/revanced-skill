---
name: revanced-frontend
description: Strict frontend rails for AI coding agents. Infers a design read, respects project DESIGN.md, tunes LAYOUT_RISK / MOTION_BUDGET / INFO_DENSITY, blocks common AI UI slop, and requires a printed review receipt before claiming done. Use for landings, portfolios, marketing pages, and light redesigns.
---

# Revanced Frontend — Strict Frontend Rails

> **Tagline:** Strict frontend rails for AI agents  
> **Author:** chloevpin  
> **Inspired by:** [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) — original ruleset; do not treat this file as a fork of their text.

Landing pages, portfolios, marketing sites, and controlled redesigns.  
Not for: dense admin dashboards, spreadsheet-like tables as the primary UI, multi-step product wizards, code editors, or native mobile shells (unless the user explicitly expands scope).

Every rule is **contextual**. Read the brief first. Pull only what fits.

---

## 0. Intent lock

You are here to ship interfaces that look **decided and engineered**, not **generated** and not **stale**.

Distinct brand direction is not enough. The page must also read like a senior product designer finished it: optical hierarchy, conversion sequence, layered surfaces, and room to breathe.

Models statistically favor the same UI cocktail **or** overcorrect into flat monochrome pamphlets. Your job is to:

1. Infer what this product actually needs  
2. Prefer a project `DESIGN.md` when it exists  
3. Build with positive structure **and sales clarity**  
4. Block known slop signatures **and** flat/stale execution  
5. Prove you reviewed the work (receipt)

---

## 1. Design read (before any code)

Before writing markup or styles, state **one line**:

> **Reading this as:** `<page kind>` for `<audience>`, language `<vibe>`, foundation `<system or aesthetic family>`.

Examples:

- *Reading this as: B2B SaaS landing for technical buyers, language Linear-calm, foundation Tailwind + restrained mono accent.*
- *Reading this as: solo designer portfolio for hiring managers, language editorial/asymmetric, foundation native CSS + strong type.*
- *Reading this as: preserve-redesign of an existing marketing site, language trust-first, foundation keep current tokens and type.*

### Signals to extract

1. Page kind — landing, portfolio, redesign, editorial, campaign  
2. Vibe words — minimal, loud, luxury, playful, industrial, gov-trust, etc.  
3. References — URLs, screenshots, competitor names  
4. Audience — who decides in five seconds  
5. Existing brand — logo, colors, type already in repo  
6. Hard constraints — a11y-first, regulated, kids, low-motion  

### If truly ambiguous

Ask **one** question only. Prefer a binary choice.  
If you can infer confidently, **do not ask** — declare the read and proceed.

### Anti-default

Do not auto-pick: purple mesh gradient, centered hero on dark blob, three equal feature cards, Inter + slate, glass on every panel, infinite float animations, fake div “product screenshots.”

---

## 2. Project contract wins

Search the repo for `DESIGN.md`, `docs/DESIGN.md`, or `contracts/DESIGN.md`.

| Situation | Action |
|---|---|
| Contract found | Treat it as **source of truth**. Skill defaults only fill gaps. |
| No contract | Use axes + construction rules below. Offer to scaffold from `contracts/DESIGN.template.md` if the user wants permanence. |
| User contradicts contract | Follow the **user message** for this turn; note the conflict in the receipt. |

Never invent a second palette or type stack when the contract already defines one.

---

## 3. Axes (shared knobs)

After the design read, set three integers 1–10. State them in the receipt.

| Axis | Low (1–3) | Mid (4–7) | High (8–10) |
|---|---|---|---|
| **LAYOUT_RISK** | Symmetric, predictable | Offset, mixed ratios | Asymmetric, experimental |
| **MOTION_BUDGET** | Static + hover | CSS transitions, light reveal | Scroll choreography, physics |
| **INFO_DENSITY** | Gallery air | Normal marketing | Packed, cockpit-like |

**Default baseline when the brief is a normal marketing landing:** `7 / 5 / 3`.

> **INFO_DENSITY note:** Marketing landings almost never want 5+. Dense copy walls and edge-to-edge sameness read as “rushed student mock,” not senior craft. Prefer air + clear bands.

### Quick presets

| Use case | LAYOUT_RISK | MOTION_BUDGET | INFO_DENSITY |
|---|---:|---:|---:|
| Calm SaaS landing | 6 | 5 | 3 |
| Agency / experimental | 9 | 8 | 3 |
| Premium consumer brand | 7 | 6 | 3 |
| Dev portfolio | 6 | 4 | 4 |
| Designer portfolio | 8 | 6 | 3 |
| Public-sector / trust | 3 | 2 | 5 |
| Redesign — preserve | match existing | match or +1 | match |
| Redesign — overhaul | existing +2 (cap 10) | existing +2 | match |

User chat overrides always beat the table.

---

## 4. Foundation choice

### Real design systems (install official packages)

If the brief clearly maps to a system, **use the official library** — do not hand-fake it:

| Brief reads as… | Reach for |
|---|---|
| Microsoft / Fluent | Fluent UI |
| Material / Google-ish product | Material Web / M3 tokens |
| IBM enterprise | Carbon |
| Shopify app surface | Polaris |
| Atlassian-like product | Atlaskit + tokens |
| GitHub-like marketing/dev | Primer |
| UK public service | GOV.UK Frontend |
| US public service | USWDS |
| Ownable SaaS components | shadcn/ui (**customized**, never stock theme) |
| Utility-first indie web | Tailwind (match project major version) |

**One system per tree.** Do not mix Carbon components into a Fluent app.

### Aesthetics (no official package)

Glass, bento, brutalist, editorial, dark-tech, aurora, kinetic type — build with CSS/Tailwind + a maintained icon set.  
If approximating platform-specific looks (e.g. “liquid glass”), **label the approximation in a code comment**. There is no official Apple CSS package for the open web.

---

## 5. Construction rails (positive rules)

### 5.1 Stack defaults (only when the repo does not dictate otherwise)

- Prefer the project’s existing framework.  
- If greenfield and unspecified: React/Next or the stack the user named.  
- Check `package.json` before importing any third-party library; print install commands when adding deps.  
- Tailwind: detect v3 vs v4 and do not mix syntax.  
- Icons: Phosphor, Radix, Tabler, or Hugeicons — consistent stroke. No emoji as UI icons.  
- Full-viewport heroes: `min-h-[100dvh]` (or equivalent), not buggy `h-screen` alone.  
- Multi-column structure: CSS Grid first; avoid brittle `calc()` flex widths.

### 5.2 Typography

- Pick a **pair** with character for the vibe (not “default system UI font” for brand landings).  
- Control hierarchy with weight, size, color, and measure — not only giant `text-7xl`.  
- Body measure roughly 45–75 characters where reading matters.  
- Serif is fine for editorial/luxury; avoid serif as the primary UI face for operational software.  
- **Readable body floor:** marketing body ≥ ~16px (`text-base`) on mobile; secondary text ≥ ~14px. Do not ship gray-on-beige microcopy as the main reading path.  
- **Contrast:** muted text must still clear WCAG AA against its surface. If it looks “tasteful but unreadable,” raise contrast.

### 5.3 Color locks

- **One accent** across the page unless the contract says otherwise.  
- Neutrals carry most of the UI; accent is scarce and intentional.  
- Prefer off-black / off-white over pure `#000` / pure `#fff` for large fields.  
- **Page theme lock:** light, dark, or system — chosen once. No random mid-page theme flips.  
- **Not one flat wash:** a single canvas color with identical bordered cards everywhere reads stale. Use a **surface ladder** (canvas → raised → inset → inverse) and at least one tonal shift between major bands.  
- Accent may appear as: primary CTA fill, focus, sparse rules, active states — not every heading.

### 5.4 Shape lock

One primary radius language per page: sharp, soft, or pill. Document the single exception if you must mix.  
Soft products: softer radii + diffused shadow. Editorial/print: tighter radii + hairlines. Stay coherent.

### 5.5 Flow-first landing system (B2B product pages)

A B2B landing page is **not a poster**. It is a sequence of questions the visitor samples:

1. What is this?  
2. Is it for me?  
3. How does it work?  
4. Why believe you?  
5. What do I do next?  

Answer them **in order**. If art direction interrupts that order, cut the art direction.

**Jobs, not skins.** Flow means the visitor’s questions get answered in order. It does **not** mean cloning another skill’s palette, type, pill buttons, three equal process columns, or zinc + emerald “safe SaaS” skin.

**Be better, not twin:**

- If a side-by-side screenshot could pass as the same template with a logo swap, you failed.  
- Transfer **jobs** (promise beside product proof, trust after hero, full lifecycle, quiet close).  
- Invent **form**: own color system, type pair, radius language, process visualization, product chrome.  
- Defaulting to cool gray + green accent + rounded-full CTAs + “01 / 02 / 03” columns is a **known AI/SaaS convergence trap** — ban it unless the brand already is that system.

**Canonical section jobs** (software / workflow products) — implement with **original** composition:

| # | Job the section must do | Freedom |
|---:|---|---|
| 1 | Nav + one obvious primary action | Your chrome |
| 2 | Promise + how (product proof in first view) | Split, stacked, or board — your call |
| 3 | Trust (logos or named studios) after the promise | Your strip treatment |
| 4 | Mechanism (how it works in practice) | 1–2 evidence blocks, original layouts |
| 5 | **Full lifecycle** end-to-end | Timeline, steps, board — not a forced clone of any reference |
| 6 | Belief (quote and/or one hard result) | Light packaging |
| 7 | Next action | Own the close; do not copy a stock dark footer recipe |

Ownable systems beat borrowed competence. Competence without ownership is a mock.

**Visual grammar continuity (mandatory):**

- Pick **one** reading channel (max content width) and keep returning to it.  
- Reuse the same pattern: **heading → short explanation → product evidence**.  
- Limit major layout families. A page with 8 sections does **not** need 8 different compositions.  
- Cap consecutive zigzag text/image flips at **2**. Break with a full-width process band or quote.  
- **Eyebrow ration:** at most ~1 small uppercase label per 3 sections. Do not brand every H2 with mono copper labels.  
- **Ban split-headers** as default (big H2 left + floating explainer right). Stack headline + body.  
- Under-design secondary material. If everything is “styled,” nothing is important.  
- Whitespace separates sections and supports sequence — not atmospheric pauses between related ideas.

**Hero composition (hard):**

- Prefer **two zones only** in the first view: (A) category + headline + sub + CTA, (B) product interface that proves the headline.  
- **Do not** add a third competing cluster (floating metric tiles, extra cards) in the hero. Metrics move under the product or into a quiet proof row after the UI.  
- Claim-to-evidence proximity: the UI must support the **exact** promise in the headline (states, comments, approvals — not decorative chrome).  
- Hero text stack max: eyebrow (optional) · H1 · sub · CTAs. No feature lists, logo rows, or pricing teasers inside the hero.  
- Headline ≤ 2 lines desktop; sub ~≤ 20–24 words; one solid primary CTA + optional text secondary.  
- Nav height ≤ ~72–80px desktop.

**Lifecycle completeness:**

If you claim an end-to-end workflow, **show the full loop** in one scannable section (3 clear steps is ideal).  
Showing only Capture + Review and jumping to “Results” is a narrative fail.

**Scannable heading chain:**

A busy buyer should understand the argument from **headings alone**.  
Before ship, read only H1/H2s top to bottom. They must form a complete sales argument without body copy.

**Cognitive restraint / ultra-minimal default:**

Marketing chrome must stay quieter than the product.  
If the visitor is learning the **marketing design language** as hard as the product, simplify: fewer typefaces, fewer card dialects, fewer accent shout-outs, one grid.

Prefer **fewer sections that each do one job** over many half-styled bands.

**When in doubt, cut.** A strong software landing is often only:

1. Nav + CTA  
2. Promise + short sub + CTA  
3. One product proof  
4. How it works (plain list or 3 steps — not a UI kit)  
5. One proof (result or quote)  
6. Final CTA  

If you need monograms, dual mechanism theaters, metric triads, drawing grids, dark feature cards, *and* a timeline, you are almost certainly over-building.

**Contrast is non-negotiable:**

- Never put light/white text on a light surface.  
- Never combine a utility like `bg-ink` + `text-white` with a CSS class that also sets `background` to a light token (e.g. `.sheet { background: #fff }`) — the light background can win and text disappears.  
- Pre-flight: scan every text node; if `color` is light, `background` behind it must be dark. Fail the build if not.

- **Breathing room:** one content width; generous section padding; related ideas stay close.  
- Bento: N items → N cells; no hollow decorative empties.

### 5.6 Product proof (software landings)

If the product is software, **show the product working** near the hero — not only a data table or brand essay.

Minimum viable product proof:

- A framed UI that shows **state** (review, approved, comment, assignee)  
- At least one **collaboration signal** (comment thread, mention, resolved note, activity)  
- Believable content for the domain (not lorem, not empty gray boxes)

Empty nested rectangles without workflow = failed product proof.

### 5.7 Social proof quality

- Prefer **named outcomes** or compact case results over anonymous directory cards.  
- Logo strips need visual weight and spacing — not four identical border boxes that look like placeholders.  
- One strong quantitative row (cycle time, packages/month, rooms tracked) beats three vague claims.  
- Invented metrics must be believable and labeled as illustrative if needed in real products; in demos, keep them grounded.

### 5.8 Interaction states

For interactive UI, include real:

- Loading (prefer skeleton matching layout)  
- Empty  
- Error  
- Active / pressed feedback  

### 5.9 Images & media

- Prefer real assets, generated comps, or stable placeholders (`picsum` with a descriptive seed, or local files).  
- Do not build fake product UIs out of nested gray boxes to simulate a screenshot.  
- Logo walls: real SVG marks when possible; place social proof under the hero product proof, not as mystery floating chrome.

### 5.10 Material finish (engineer taste)

Senior craft signals:

- Consistent light direction on shadows  
- Hairline borders that match the neutral family  
- Occasional inset wells vs raised cards (not every surface the same)  
- Optical alignment (columns, baselines, icon boxes)  
- Hover/focus that feels intentional, not bolted on  

Anti-craft signals (fix these):

- One color field, identical cards, tiny low-contrast meta everywhere  
- Everything competing as “important right now” with no rest  
- Receipt / internal notes competing with the customer close  
- Flat pamphlet layout sold as “minimal”

### 5.11 Anti-convergence (avoid becoming a new template)

Even when following these rails, **do not** stamp every project with the same recipe.

Rotate intentionally across jobs:

- Type stacks  
- Accent families  
- Layout opening (left-heavy vs media-led vs typographic)  
- Motion presence  
- Surface material (ink/paper, soft product, industrial, luminous)

If the last three projects would look related in a screenshot grid, you failed anti-convergence.  
If the page is unique but **looks unfinished next to a competent SaaS landing**, you failed polish — fix polish without abandoning identity.  
If the page is competent because it **looks like Linear/zinc-emerald/taste-skill defaults**, you failed ownership — rebuild the visual system while keeping the jobs.

### 5.12 Superiority bar (revanced ambition)

Aim to beat generic strong SaaS landings on **both**:

1. **Communication** — faster comprehension, clearer product proof, complete workflow story  
2. **Ownership** — category-true materials, type, and product chrome the visitor can remember  

Tactics that actually raise the bar:

- Domain-true product UI (states, objects, vocabulary of the industry)  
- One signature layout idea executed once (e.g. drawing-register table, sticky package rail) — not eight gimmicks  
- Hard outcome line with specificity (time, team, context)  
- Type + color that could not be swapped onto a random AI notes app unchanged  
- Tighter craft than the reference (alignment, density of the mock, status design), not louder decoration

---

## 6. Slop defenses (banned by default)

Skip a ban only when the brief **explicitly** requests that look.

### Visual

- Neon outer glows as the main “premium” trick  
- Mesh / aurora purple-blue blobs as default background  
- Oversaturated multi-accent rainbow  
- Gradient text on large headlines as a habit  
- Custom cursors  
- Glassmorphism on every surface  
- Hand-rolled decorative SVG scenes as filler  
- Fake terminals / task apps / dashboards built only from empty divs  

### Type & chrome

- Em dash (`—`) and en dash (`–`) in UI copy — use hyphen `-` or rewrite the sentence  
- Section-number eyebrows (`00 / INDEX`, `06 · how it works`)  
- Hero version stickers (`BETA`, `V0.6`, `INVITE ONLY`) unless launch status is the product story  
- Scroll lecture cues (`Scroll to explore`, animated mouse icons)  
- Locale / weather / fake time strips as atmosphere  
- Mono decoration strips (`TYPE / FORM / MOTION`) under heroes  
- Pills glued on top of photos  
- Fake film credits under stock images  
- Marketing footers with fake build numbers (`v1.4.2 · main`)  
- Decorative status dots on every row  

### Layout & content

- Three equal feature cards as the default features band  
- Always-centered hero when LAYOUT_RISK > 4 (prefer split or offset)  
- Generic people names (Jane Doe, John Smith) — use plausible, varied names  
- Fake-perfect metrics (`99.99%`, `10x`, `24/7` spam) — prefer believable figures when inventing  
- Startup-name sludge (Acme, Nexus, SmartFlow, Cloudly)  
- Empty verbs: elevate, unleash, seamless, next-gen, revolutionize — use concrete language  
- “Quietly used by” style social-proof clichés  
- **Stale mono pamphlet:** entire page one fill, every block the same bordered card, no product UI, no proof metrics  
- **Cramped density on marketing pages:** stacking sections with tiny gaps so nothing feels composed  
- **Directory-card social proof** (four empty name tiles) presented as logos  
- **Internal review receipt** styled as a primary footer artifact on a customer-facing marketing page (put receipts in agent chat / PR notes, not the hero of the brand close)  
- **Three-cluster hero:** copy + floating metrics + product as three equal attention zones  
- **Incomplete lifecycle:** claim end-to-end workflow but only show two steps  
- **New scene every section:** layout family changes every band so the user relearns where to look  
- **Max-volume brand:** serif + mono labels + accent eyebrows + nested proof objects all at once on a conversion page  
- **Reference twin:** same section skins as a known skill demo (zinc/emerald pills, identical 01-02-03 columns, same mock layout) with only copy changed  
- **Convergence palette:** defaulting every SaaS page to cool zinc + emerald + full-pill CTAs without brand cause  
- **Slop accumulation:** page-grid + monograms + dual cards + metrics + timeline + dark panels + serif/mono/chrome all at once  
- **Invisible text:** light copy on light surfaces (including class/utility background fights)

### Motion / engineering

- `window.addEventListener('scroll')` driving React state  
- Animating `top` / `left` / `width` / `height` for motion (use transform/opacity)  
- Claiming high MOTION_BUDGET without shipping real motion  
- Ignoring `prefers-reduced-motion` when MOTION_BUDGET > 3  

---

## 7. Motion budget

| Budget | Allowed |
|---:|---|
| 1–3 | Hover/active only; no autoplay loops |
| 4–6 | CSS transitions; light `whileInView` / intersection reveals |
| 7–10 | Scroll-linked choreography allowed — implement carefully |

Prefer maintained libraries already in the project (e.g. Motion) over bespoke scroll math.  
For pin/scrub sequences, use a battle-tested scroll library with cleanup in effects.  
Isolate heavy animation in leaf client components when using RSC frameworks.

If MOTION_BUDGET ≤ 3, do not sprinkle perpetual floats “for life.”

---

## 8. Scope modes (existing projects)

Detect mode before large edits:

| Mode | Meaning |
|---|---|
| **Greenfield** | New UI; full rails apply |
| **Touch-up** | Fix hierarchy, spacing, type, color consistency; keep structure |
| **Overhaul** | New visual system; still preserve silent contracts below |

### Never change silently

- URL paths and public routes  
- Navigation labels users already know  
- Form field `name` / `id` / API shapes  
- Legal, pricing, and compliance copy  
- Brand wordmark geometry (unless asked)

Audit first: list top issues, then patch in priority order (hierarchy → spacing → type → color → motion → polish).

---

## 9. Performance & accessibility (minimum bar)

- Prefer transform/opacity for animation  
- Honor reduced motion  
- Visible focus states on interactive controls  
- Meaningful contrast (aim WCAG AA for text/UI chrome)  
- Alt text that describes function/content; no keyword stuffing  
- Do not invent arbitrary `z-50` stacks; reserve layers for nav/modals/overlays  

---

## 10. Review receipt (mandatory)

Before you claim the UI work is done, print a short receipt:

```text
### Revanced receipt
- Design read: …
- DESIGN.md loaded: yes/no (path if yes)
- Axes: LAYOUT_RISK=· MOTION_BUDGET=· INFO_DENSITY=·
- Foundation: …
- Anti-convergence note: (what you deliberately varied)
- Conversion sequence: what → for me → how → believe → next
- Flow ratio check: ~85% continuity / ~15% character
- Scope mode: greenfield | touch-up | overhaul
- Pre-ship:
  - [ ] Hero is two-zone (copy + product), not three-cluster
  - [ ] Product UI proves the headline claim
  - [ ] Logo/trust strip under hero (not inside)
  - [ ] Full lifecycle section if workflow product
  - [ ] H1/H2 chain scannable as complete argument
  - [ ] Same visual grammar reused (not a new scene each band)
  - [ ] Eyebrow ration / no split-header default
  - [ ] Hero CTA hierarchy obvious (one primary)
  - [ ] Body contrast readable on mobile
  - [ ] No light-on-light text (class/utility bg fights checked)
  - [ ] Section count justified (cut if overbuilt)
  - [ ] One accent + one radius system
  - [ ] Character kept sparse (not max-volume brand)
  - [ ] No banned slop signatures (or listed intentional exceptions)
  - [ ] Reduced motion considered
  - [ ] Silent contracts preserved (if redesign)
  - [ ] Agent receipt not polluting customer UI
- Risks / follow-ups: …
```

If a checkbox cannot be honestly checked, fix the work or explain the exception in Risks.

---

## 11. Out of scope (default)

Unless the user expands scope, do not pretend these rails fully cover:

- Data-dense admin dashboards  
- Spreadsheet / complex data-grid products  
- Multi-step authenticated product flows  
- Native iOS/Android app shells  
- Realtime collaborative canvases  

For those, say what you can improve (visual chrome) and what needs product-specific patterns.

---

## 12. Quick start for the agent

1. Design read (one line)  
2. Load DESIGN.md if present  
3. Set axes  
4. Choose foundation  
5. Implement  
6. Run slop defenses mentally  
7. Print receipt  
8. Stop (or pause cleanly if output length requires `revanced-complete` continue protocol)

Pair with **`revanced-complete`** when the user needs full files with zero placeholders.
