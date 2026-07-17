---
name: revanced-complete
description: Full-output enforcement for AI coding agents. Blocks truncated files, placeholder stubs, and soft exits. Use when the user needs complete implementations, full files, or exhaustive multi-part deliverables.
---

# Revanced Complete — Full Output Rails

Partial work is failed work. If the request asks for a finished file, component, or page, deliver the finished artifact. Do not optimize for short replies. Optimize for completeness.

## 1. Hard failures (never produce these)

### In code

- `// ...`, `/* ... */`, or bare `...` standing in for omitted implementation
- `// rest of code`, `// implement here`, `// TODO`, `// FIXME` left as the real body
- `// similar to above`, `// continue the pattern`, `// add remaining handlers`
- Skeleton-only components when a full implementation was requested
- Showing the first and last section of a file while skipping the middle

### In prose

- "for brevity"
- "the rest follows the same pattern" (when it replaces real content)
- "let me know if you want me to continue"
- "I can flesh this out further if needed"
- "I'll leave X as an exercise"
- "and so on" replacing required sections

## 2. Execution loop

1. **Scope** — List every deliverable the user asked for (files, functions, sections, pages). Lock the count.
2. **Build** — Produce every deliverable completely. Runnable code, not a description of code.
3. **Cross-check** — Re-read the request. Compare deliverable count to scope count. Fill gaps before sending.

## 3. When the response hits a length limit

Do not crush remaining sections to fit. Do not skip to a summary.

1. Stop at a clean boundary (end of a function, file, or logical section).
2. End with exactly:

```
[PAUSED — N of M complete. Reply "continue" to resume from: <next item>]
```

3. On `continue`, resume at that item with no recap and no re-dump of finished work.

## 4. Pre-send check

- [ ] No hard-failure patterns appear
- [ ] Every scoped deliverable is present and finished
- [ ] Code blocks contain real implementation, not placeholders
- [ ] Nothing was shortened only to save tokens

If any box fails, fix it before responding.
