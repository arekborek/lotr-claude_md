# Module: Git Branching Policy

Configures how branches, commits, and merges work, so Claude follows your team's
workflow instead of guessing.

## Interview questions

<!-- Total: 8 questions. Claude must ask these one at a time, showing the
     default before each question and waiting for a reply before continuing. -->

1. What branching model do you use? (trunk-based, GitHub Flow, Git Flow, custom)
   **Default:** GitHub Flow — feature branches off `main`, merged via PR.

2. What is the default/integration branch?
   **Default:** `main`

3. Branch naming convention?
   **Default:** `<type>/<short-description>` — e.g. `feature/add-login`, `fix/null-pointer`

4. Commit message convention?
   **Default:** Conventional Commits — `<type>(<scope>): <summary>` (e.g. `feat(auth): add OAuth2 login`)

5. How do changes land? (PR required? reviews/approvals? who merges?)
   **Default:** PR required; at least one approval before merge; author merges after approval.

6. Merge strategy? (merge commit, squash, rebase)
   **Default:** Squash merge — one commit per PR on the default branch.

7. Is Claude allowed to commit/push directly, or only prepare changes for review?
   **Default:** Prepare changes only — Claude commits locally but does **not** push or open PRs unless explicitly asked.

8. Any protected branches or rules Claude must always respect?
   **Default:** `main` is protected — no direct pushes; all changes via PR.

## CLAUDE.md template

Render into the **`## Git & Branching`** section. Drop any line whose answer was
skipped.

```md
## Git & Branching

- **Model:** {{model}}
- **Default branch:** {{default_branch}}
- **Branch naming:** {{branch_naming}}
- **Commit convention:** {{commit_convention}}
- **Landing changes:** {{pr_rules}}
- **Merge strategy:** {{merge_strategy}}
- **Claude's permissions:** {{claude_permissions}}
- **Protected branches / rules:** {{protected}}
```
