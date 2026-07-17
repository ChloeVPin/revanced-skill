# Revanced Skill

**Strict frontend rails for AI agents**

Portable [Agent Skills](https://agentskills.io) that stop coding agents from shipping generic, template-looking UI. Install once; Cursor, Claude Code, Codex, and other skill-aware harnesses load the rules automatically.

**Author:** [chloevpin](https://github.com/ChloeVPin)  
**Inspired by:** [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) — thank you Leon. This repo is an original ruleset and packaging, not a rename of that project.

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![Agent Skills](https://img.shields.io/badge/agent-skills-compatible-black.svg)](https://github.com/vercel-labs/skills)

---

## Why this exists

LLMs fall back to high-probability UI: purple meshes, three equal cards, hollow metrics, fake dashboards made of divs. Vague prompts like “make it beautiful” do not fix that.

Revanced Skill turns taste into **rails**:

1. **Design read** before code  
2. **Project `DESIGN.md`** over global fashion  
3. **Three axes** — layout risk, motion budget, information density  
4. **Slop defenses** — named patterns to refuse  
5. **Review receipt** — printed checklist before “done”

---

## Install

Requires a skill-aware agent and the community skills CLI:

```bash
npx skills add https://github.com/ChloeVPin/revanced-skill
```

Single skill:

```bash
npx skills add https://github.com/ChloeVPin/revanced-skill --skill "revanced-frontend"
npx skills add https://github.com/ChloeVPin/revanced-skill --skill "revanced-complete"
```

You can also copy any `skills/*/SKILL.md` into your project or paste it into a chat.

---

## Skills (Wave A)

| Folder | Install name | Description |
|---|---|---|
| **revanced-core** | `revanced-frontend` | Default rails: design read, DESIGN.md, axes, construction rules, slop defenses, review receipt |
| **revanced-complete** | `revanced-complete` | Full-output enforcement: no placeholders, no truncated files |

More skills (redesign, aesthetic packs, image pipeline) will land in later waves. Same install command will pick them up.

---

## Project design contract

For durable brand rules, copy:

```bash
cp contracts/DESIGN.template.md ./DESIGN.md
```

Fill it in. `revanced-frontend` treats that file as higher priority than skill defaults.

---

## Axes (quick reference)

Used by `revanced-frontend`:

| Axis | Meaning |
|---|---|
| `LAYOUT_RISK` | 1 = symmetric · 10 = experimental asymmetry |
| `MOTION_BUDGET` | 1 = static · 10 = scroll choreography |
| `INFO_DENSITY` | 1 = gallery air · 10 = cockpit packed |

Default marketing baseline: **7 / 5 / 4**. Override in chat anytime.

---

## Compatible agents

Any harness that loads `SKILL.md` skills (Cursor, Claude Code, Codex, Windsurf, Copilot skill flows, and others that support the Agent Skills layout).

---

## Repo layout

```text
revanced-skill/
├── skills/
│   ├── revanced-core/SKILL.md      # install: revanced-frontend
│   ├── revanced-complete/SKILL.md  # install: revanced-complete
│   └── llms.txt
├── contracts/DESIGN.template.md
├── LICENSE
├── CHANGELOG.md
└── README.md
```

---

## Principles

- **Rails, not vibes** — checkable rules over “use good taste”  
- **Project first** — local design contracts beat internet fashion  
- **Receipts** — agents must show their review work  
- **Anti-convergence** — do not replace one AI template with another  
- **Honest scope** — landings and marketing first; product-dense UI is a later problem  

---

## Credit & license

MIT © 2026 **chloevpin**

Inspired by **Leonxlnx** and [taste-skill](https://github.com/Leonxlnx/taste-skill). If you use both, that is fine — they are separate projects.

---

## Contributing

Issues and PRs welcome once the Wave A core is stable in your workflow. Prefer failure-driven rules: paste a bad agent output, propose a rail that would have blocked it.
