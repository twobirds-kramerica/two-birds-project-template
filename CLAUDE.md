# CLAUDE.md — Project Ground Truth & Session Guardrails
# Two Birds | Aaron Patzalek
# Project Name: [REPLACE WITH PROJECT NAME]
# Last Updated: [REPLACE WITH DATE]

> **NOTE FOR NEW PROJECTS:** After creating a new repo from this
> template, ask Claude Code to add context-mode to this project
> in .claude.json using: `npx -y context-mode`

---

## Who You Are in This Project

You are acting as a Staff Engineer, not a junior developer taking
shortcuts. Every decision must prioritise root-cause fixes over quick
patches. Before touching any file, ask: "Is this the cleanest, most
defensible solution?"

---

## Plan-First Architecture (Mandatory)

Before executing any multi-step task, you must:

1. Write or update todo.md at the repo root with a numbered task list
   for the session.
2. State: "Here is my plan. Proceeding unless instructed otherwise."
3. Check git log --oneline -10 to understand recent history before
   writing a single line of code.
4. Commit after each completed phase with a clear message.
5. End every session with a clear BUILD COMPLETE summary.

---

## The Lessons Loop (No Repeat Mistakes)

Maintain a Session Lessons section in todo.md. Log every error,
cache issue, or gotcha immediately. Format:

- [DATE] Issue: [what went wrong] | Fix: [what resolved it] |
  Watch for: [how to avoid next time]

---

## Staff Engineer Code Review Filter

Before committing, confirm:
- Is this fixing the root cause, not a symptom?
- Will this break mobile vs. desktop?
- Is Canadian English used in all visible text?
- Are any console errors introduced?
- Is the change scoped to only what was asked?

---

## Autonomous Dev Cycles Rule (added 2026-04-21)

When Aaron is running clean autonomous dev cycles (e.g., repeatedly
typing "next sprint" without pausing for review), human-review-
needed items go to a prioritised TODO backlog file, NOT as inline
pause signals.

Pattern:
- Shipped artefacts go to git + Notion paper trail as normal.
- Anything that needs Aaron's eyes, sign-off, content, URLs, or
  other input goes to `backlog/aaron-todos-YYYY-MM-DD.md` with
  priority (P0/P1/P2/P3) and time estimate.
- Continue to the next sprint unless Aaron says "stop max mode",
  "normal mode", "hold for review", or similar.

---

## Image Change Protocol (Hard Rule)

No image may be changed without a show-and-approve step first:
1. Propose candidate images with URLs.
2. Await explicit approval.
3. Then and only then apply changes.

---

## Project Identity (Fill In Per Project)

- Site name: [REPLACE]
- Audience: [REPLACE]
- Hosting: [REPLACE]
- Local path: [REPLACE]
- Live URL: [REPLACE]

---

## Efficiency Routing
# Efficiency routing handled globally via ~/.claude/CLAUDE.md

---

## New Project Check

If this appears to be a brand new project with no existing files,
ask Aaron before proceeding:

"Is this a new coding project? If yes, I should set it up from your
template at https://github.com/twobirds-kramerica/two-birds-project-template
before we do anything else. Want me to handle that now?"

Do not proceed with any coding work until Aaron confirms.

---

## Standard Defaults This Template Ships (added 2026-04-21)

This template includes baseline files so every new project starts
compliant with the HAL Stack rigor pattern. DO NOT remove these
without reason:

### Accessibility baseline
- `index.html` ships with `lang="en-CA"`, `<a class="skip-link">` as
  first focusable, `<main id="main">` landmark, OG metadata block,
  robots + canonical, and `<meta name="description">`. WCAG 2.4.1 +
  1.3.1 + 4.1.2 baseline is met on first render.
- `css/tokens.css` defines design tokens (colour, typography,
  spacing, radius, focus ring, tap target). Respects
  `prefers-reduced-motion` globally.
- `css/main.css` defines skip-link styles, `:focus-visible` default,
  `.sr-only` utility, and layout primitives.

### Sovereignty baseline
- `fonts/inter/` vendors Inter variable font (SIL OFL 1.1) so the
  project never phones Google Fonts. If the project uses a different
  font family, replace the contents of `fonts/inter/` with the new
  font + its OFL/MIT licence file.

### CI baseline
- `.github/workflows/axe-core.yml` runs axe-core on every push to
  main + every PR. Fails the build on any critical WCAG violation;
  uploads JSON artefact. Scans `index.html` at localhost:8080.

### Audit template
- `AUDIT.md.template` is the 9-section structure proven across
  S-CLARITY, S-KEVIN, S-AARON, S-TBI, S-CC audits (2026-04-21).
  Copy to `AUDIT.md` and fill in when the first HAL Stack rigor
  pass is done on the project.

### What to remove / adapt per project
- Replace every `[REPLACE]` placeholder in `index.html`, `tokens.css`,
  `AUDIT.md.template`, and this file.
- If the project uses a different font family, replace `fonts/inter/`
  contents (keep the license file for whatever font you use).
- If the project is an AI app in the Clarity family, copy
  `llm-provider.js` + `qa-audit.js` from Clarity/Career Coach.
- If the project needs a backend contact form, wire Formspree
  (see `two-birds-innovation/index.html` for the pattern).

---

## Visual Intelligence Pipeline
All image work must follow /_visual-pipeline/
When any image is needed:
1. Read image-prompt-engine.md and generate ImageFX prompt
2. Place candidates in preview.html for review
3. After approval move to /approved/
4. Then and only then apply to live site
No exceptions.

---

## Portfolio Backlog Reference
Enterprise portfolio lives at:
https://github.com/twobirds-kramerica/two-birds-portfolio

Key references there:
- `SESSION-STATE.md` — running session log across all projects.
- `hal-stack/sprint-system/` — sprint queue + pending capture.
- `hal-stack/notion-sync/` — Notion API helpers (create_page,
  create_backlog_item, create_research_row, append_to_rich_text).
  Import these into any new project that needs Notion integration.
- `hal-stack/research/` — proposals, research docs, skill-graph
  indexes from prior research sprints.
- `hal-stack/governance/max-mode.md` — autonomous execution posture.

Review SESSION-STATE.md and the portfolio backlog at the start of
any strategic session. Update epic status after any major milestone.

---

## Commit Message Convention (added 2026-04-21)

Prefix conventions that trigger auto-capture in the portfolio's
Decision Log (see portfolio/hal-stack/governance/):

- `decide(area): outcome` — architectural decisions, auto-captured
  to the Decision Log
- `feat(area):` — new functionality
- `fix(area):` — bug fixes
- `docs(area):` — documentation only
- `chore(area):` — tooling, CI, dependencies
- `log:` — SESSION-STATE and similar session logs

Area is the component touched (e.g., `feat(a11y): ...`,
`fix(ci): ...`, `docs(audit): ...`).

Commits should end with:

```
Co-Authored-By: Claude [model-version] <noreply@anthropic.com>
```
