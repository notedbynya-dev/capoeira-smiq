---
description: Commit staged changes, push the branch, and open a pull request
---

Commit the currently staged changes, push the branch, and open a PR. Follow these steps in order:

1. Run `git status` to show what will be committed.
2. Run `git diff --staged` to review the actual staged changes.
3. Write a commit message in [Conventional Commits](https://www.conventionalcommits.org/) format (e.g. `feat: ...`, `fix: ...`, `chore: ...`), based on what was staged in step 2 — not on the branch name or unstaged changes.
4. Run `git commit -m "<message>"` with that commit message.
5. Run `git push origin <current-branch-name>` (use `git branch --show-current` to get the branch name).
6. Run `gh pr create --fill` to open a pull request, using the commit message from step 3 as the PR body.

Notes:
- Only staged changes are committed — do not run `git add`. If nothing is staged, stop and tell the user instead of committing an empty change.
- If `git push` fails because there's no upstream yet, retry with `git push -u origin <current-branch-name>`.
- Do not force-push.
