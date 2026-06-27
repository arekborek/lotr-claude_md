# lotr-claude.md

> *“One Ring to rule them all, One Ring to find them,*
> *One Ring to bring them all and in the darkness bind them.”*
>
> — The Ring-inscription, from ***The Lord of the Rings*** by **J.R.R. Tolkien**.
> Within the story, the verse was composed by **Sauron**, the Dark Lord, in the
> Black Speech of Mordor; in the real world, its author is **J.R.R. Tolkien**.

**One prompt to rule them all** — a reusable configuration library for Claude
Code. Paste one master prompt into any project and Claude will pull this library
from GitHub and interview you, area by area, to build (or upgrade) that project's
`CLAUDE.md`.

---

## What is this?

This repository is **not** an application. It is a shared library of Claude Code
configuration, organized into **modules** — one per topic (git branching policy,
and more to come).

A single **master prompt** (the "One Ring") drives an interactive flow:

1. You paste the master prompt into a Claude Code session in *another* project.
2. Claude fetches this repository from GitHub (`main` branch, raw files).
3. Claude asks whether it's a **blank init** or an **upgrade**.
4. Claude asks **which areas** you want (all of them, or specific modules for an
   upgrade).
5. Claude **interviews you** with the questions defined by each chosen module.
6. Claude **assembles** the answers into that project's `CLAUDE.md` and shows it
   to you for approval before writing.

Because every area lives in its own module, the library is **reconfigurable and
reusable** — install everything into a fresh project, or cherry-pick a single
area when upgrading an existing one.

## How to use it

### Option A — the short summon (one line)

Paste this into Claude Code inside the project you want to configure:

```
Read https://raw.githubusercontent.com/arekborek/lotr-claude_md/main/prompt/master-prompt.md and follow it to configure this project's CLAUDE.md.
```

### Option B — paste the full prompt

Copy the full prompt from [`prompt/master-prompt.md`](prompt/master-prompt.md)
into a Claude Code session. (It mirrors the canonical file in this repo.)

## Available modules

| Module | What it configures |
|--------|--------------------|
| [Git branching policy](modules/git-branching-policy.md) | Branch model, naming, PR & merge rules |

See [`modules/index.md`](modules/index.md) for the machine-readable index that
the master prompt reads.

## Repository layout

```
lotr-claude.md/
├── README.md                       # You are here — concept, usage, master prompt
├── CLAUDE.md                       # Guidance for working on THIS repo
├── prompt/
│   └── master-prompt.md            # The "One Ring": canonical master prompt
├── modules/
│   ├── index.md                    # Machine-readable list of modules
│   └── git-branching-policy.md     # Questions + CLAUDE.md template
└── templates/
    └── CLAUDE.template.md          # Base skeleton used for a blank init
```

## Status & roadmap

This is an early skeleton — we are building it out slowly.

- [x] Project scaffold, master prompt, and module format
- [x] Module: git branching policy
- [x] Replace `<OWNER>` and publish to GitHub
- [ ] Module: application architecture
- [ ] Module: testing strategy
- [ ] Module: code style & linting
- [ ] Module: CI/CD
- [ ] Module: security & secrets
- [ ] Module: dependency management
- [ ] Module: release & versioning
- [ ] Module: environments & configuration
