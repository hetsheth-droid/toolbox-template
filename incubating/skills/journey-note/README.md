# journey-note

A Claude Code slash command (`/journey-note`) that generates a narrative session summary capturing the intellectual arc of a working session.

## What it does

Produces a journey note with two complementary sections:

1. **Narrative** — Acts, arc visualization, thesis, and artifacts table. Written for humans to read and for blog content.
2. **Session Ledger** — Semantically dense, machine-optimized accounting using stable vocabulary (`DECIDED`, `FOUND`, `CREATED`, `MODIFIED`, `NEXT`, `BLOCKED`, `QUESTION`, `DEP`). Designed for cold-start resumability.

Output goes to `docs/journey-notes/YYYY-MM-DD-[title-slug].md`.

## How to use it

Copy `journey-note.md` into your project's `.claude/commands/` directory (or `~/.claude/commands/` for global availability), then invoke with `/journey-note` in Claude Code.

```bash
# Project-level
mkdir -p .claude/commands
cp journey-note.md .claude/commands/

# Global
cp journey-note.md ~/.claude/commands/
```
