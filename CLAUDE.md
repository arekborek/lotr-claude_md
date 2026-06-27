# CLAUDE.md

Guidance for Claude Code when working in **this** repository (`lotr-claude.md`).

## What this repo is

This repo is a **reusable configuration library** for Claude Code. It does **not**
contain an application. Its job is to configure *other* projects' `CLAUDE.md`
files through an interactive, interview-driven master prompt. See the
[README](README.md) for the full concept.

## Layout

- `README.md` — concept, usage, and the copy-paste master prompt.
- `prompt/master-prompt.md` — the canonical master prompt (the "One Ring"); this
  is the artifact users paste into other projects.
- `modules/` — one file per configuration area, each holding its interview
  questions and the `CLAUDE.md` template section it owns. `modules/index.md`
  lists them all.
- `templates/CLAUDE.template.md` — base skeleton used for a blank init.

## Conventions when editing

- **Modules are self-contained.** A module file = `## Interview questions` +
  `## CLAUDE.md template`. Two modules must never write the same output section.
- **Keep the master prompt in sync.** If you change the flow, update both
  `prompt/master-prompt.md` and any copy/summary of it in `README.md`.
- **GitHub owner is `arekborek`.** The raw GitHub links use this owner. If the
  repo is forked or transferred, update it in `README.md`,
  `prompt/master-prompt.md`, and `templates/CLAUDE.template.md`.
- **Canonical branch is `main`.** The raw GitHub links point at it.

## Adding a new module

1. Create `modules/<area>.md` with two sections: `## Interview questions` and
   `## CLAUDE.md template` (one owned output section).
2. Add a row to `modules/index.md`.
3. Add it to the "Available modules" list in `README.md`.

## Git & Branching

- **Model:** GitHub Flow — feature branches off `main`, merged via PR.
- **Default branch:** `main`
- **Branch naming:** `<type>/<short-description>` — e.g. `feature/add-login`, `fix/null-pointer`
- **Commit convention:** Conventional Commits — `<type>(<scope>): <summary>`
- **Landing changes:** PR required; at least one approval before merge; author merges after approval.
- **Merge strategy:** Squash merge — one commit per PR on `main`.
- **Claude's permissions:** Prepare changes only — commits locally, does not push or open PRs unless explicitly asked.
- **Protected branches / rules:** `main` is protected — no direct pushes; all changes via PR.
