Ship the current work: commit, push, and create a PR with journey note reference.

## Arguments
- $ARGUMENTS: Optional short description of the changes (used in commit message and PR title). Can include a conventional commit prefix like `feat(scope):` to set the commit type and scope.

## Steps

### 1. Survey the state

Run these in parallel:
- `git status` (never use `-uall`)
- `git diff --stat` (staged + unstaged)
- `git log --oneline -5`
- `git branch --show-current`

Determine:
- What branch are we on?
- Are there uncommitted changes?
- Is there a journey note from today in `docs/journey-notes/`?

### 2. Find today's journey note

Search for a file matching `**/YYYY-MM-DD-*.md` where the date is today. Common locations: `docs/journey-notes/`, `journey-notes/`, `docs/`. Use whichever exists, or default to `docs/journey-notes/`. If multiple exist, use the most recently modified one. If none exists, **ask the user** if they want to create one first with `/journey-note` before shipping — but don't block on it.

Store the journey note path (relative to repo root) for use in the PR description.

### 3. Create a branch if needed

If on `main` or `master`:
- Derive a branch name from $ARGUMENTS or the changes (e.g., `feature/add-oauth-flow`)
- `git checkout -b <branch-name>`

If already on a feature branch, stay on it.

### 4. Stage and commit

- Stage all modified and untracked files that are relevant to the work. Use specific file paths — never `git add -A` or `git add .`
- Do NOT stage files that look like secrets (`.env`, credentials, keys)
- Do NOT stage build artifacts (`output/`, `.build/`, `dist/`, `node_modules/`)
- Write a commit message following the repo's commit conventions (check CLAUDE.md or CONTRIBUTING.md). If none exist, use these defaults:
  - Imperative mood: "Add feature" not "Added feature"
  - Subject line ≤ 72 chars
  - Body (optional): explain why, not what — wrap at 72 chars

### 5. Push

```bash
git push -u origin <branch-name>
```

### 6. Create PR

Create a PR following the repo's PR conventions (check CLAUDE.md). If none exist, use these defaults:

```
gh pr create --title "<title under 70 chars>" --body "$(cat <<'EOF'
## Summary

<3-5 bullet points — concise, imperative, why-focused>

<If journey note exists:>
Session narrative: [`<journey-note-path>`](<journey-note-path>)
EOF
)"
```

**Important:** If a journey note exists for today, link it in the PR description.

### 7. Report

Print the PR URL and a one-line summary.

## Rules

- **Journey notes are first-class.** Always check for them. Always link them. If the session involved significant work and there's no journey note, nudge the user.
- **One commit per ship.** Don't create multiple commits — squash the work into one clean commit.
- **Never push to main directly.** Always create a branch and PR.
- **Never force push.** If the push fails, diagnose and ask the user.
- **Confirm before acting** if there are uncommitted changes that look unrelated to the current work.
