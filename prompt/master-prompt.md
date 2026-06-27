# The One Ring — CLAUDE.md Configurator (Master Prompt)

Copy everything **below the line** into a Claude Code session inside the project
you want to configure. Claude will pull this shared configuration library from
GitHub and interview you, area by area, to produce (or upgrade) that project's
`CLAUDE.md`.

---

You are setting up the `CLAUDE.md` file for **this** project using a shared
configuration library. Follow these steps precisely and interactively — never
guess an answer you can ask me for.

## 0. Source of truth

The configuration library lives at:

- **Repo:** https://github.com/arekborek/lotr-claude.md
- **Branch:** `main`
- **Raw base URL:** `https://raw.githubusercontent.com/arekborek/lotr-claude.md/main/`

Fetch files from the raw base URL above. Begin by fetching `modules/index.md`,
which lists every available configuration area (module) with a short description.

## 1. Determine the mode

Ask me which applies, and wait for my answer:

- **(a) Blank init** — this project has no `CLAUDE.md` yet, or I want to start over.
- **(b) Upgrade** — this project already has a `CLAUDE.md` and I want to add or
  refresh specific areas.

If **(b)**, read the existing `CLAUDE.md` in this project first, so you understand
what is already there before changing anything.

## 2. Choose the areas

Show me the modules from `modules/index.md`, each with its one-line description,
then ask which areas to configure:

- **Blank init:** default to *all* modules, but let me deselect any.
- **Upgrade:** ask me to pick exactly the module(s) to install or update. Leave
  every other section of the existing `CLAUDE.md` untouched.

## 3. Interview me, area by area

For each selected module, fetch its file (e.g.
`modules/git-branching-policy.md`) and ask me its interview questions.

- Do **one area at a time**, and summarize my answers back before moving on.
- Ask follow-up questions when my answer is ambiguous; never invent details.
- You may skip a question that clearly doesn't apply — but tell me you skipped it.

## 4. Assemble the CLAUDE.md

Render each module's template from my answers:

- **Blank init:** build the file from `templates/CLAUDE.template.md` plus every
  selected module's section, in index order.
- **Upgrade:** merge the new/updated sections into the existing `CLAUDE.md`.
  Replace **only** the section each chosen module owns; preserve everything else
  exactly as it was.

## 5. Review before writing

Show me the full proposed `CLAUDE.md` (or a diff, for an upgrade) and wait for my
explicit approval. Only write the file after I confirm.
