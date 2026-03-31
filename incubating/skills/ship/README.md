# /ship

Claude Code skill to commit, push, and create a PR in one command — with automatic journey note linking.

## What it does

1. Surveys git state (branch, changes, recent commits)
2. Finds today's journey note in `docs/journey-notes/`
3. Creates a feature branch if on main
4. Stages and commits with a clean message
5. Pushes and creates a PR
6. Links the journey note in the PR description

## Usage

```
/ship "feat(auth): add OAuth login flow"
```

Or without arguments — it will derive the description from the changes:

```
/ship
```

## Installation

Copy `ship.md` to your Claude Code commands directory:

```bash
cp ship.md ~/.claude/commands/ship.md
```

Or symlink it:

```bash
ln -s "$(pwd)/ship.md" ~/.claude/commands/ship.md
```

## Why journey notes matter

Every PR should link back to the session narrative that produced it. Journey notes capture the *why* — the decisions, dead ends, and insights that a diff alone can't convey. `/ship` enforces this by always looking for today's journey note and including it in the PR description.
