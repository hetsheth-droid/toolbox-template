# Claude Code Skills

Reusable slash commands for Claude Code. Each skill is a `.md` file that teaches Claude Code how to perform a specific workflow.

## Available Skills

| Skill | Command | What it does |
|---|---|---|
| [ship](ship/) | `/ship` | Commit, push, and create a PR in one command. Auto-links journey notes. |
| [journey-note](journey-note/) | `/journey-note` | Generate a narrative session summary with a machine-readable ledger. |

## Setup

### Quick start (symlink — recommended)

Symlink the skills to your Claude Code commands directory. Updates from the repo auto-apply.

```bash
# Global (works in every project)
mkdir -p ~/.claude/commands
ln -s "$(pwd)/ship/ship.md" ~/.claude/commands/ship.md
ln -s "$(pwd)/journey-note/journey-note.md" ~/.claude/commands/journey-note.md
```

### Copy (if you don't want auto-updates)

```bash
mkdir -p ~/.claude/commands
cp ship/ship.md ~/.claude/commands/ship.md
cp journey-note/journey-note.md ~/.claude/commands/journey-note.md
```

### Per-project only

```bash
mkdir -p .claude/commands
ln -s "$(pwd)/ship/ship.md" .claude/commands/ship.md
```

## Usage

Once installed, use them in any Claude Code session:

```
/ship "feat(auth): add OAuth flow"
/journey-note
```

`/ship` pairs with `/journey-note` — ship looks for today's journey note and links it in the PR description.

## Contributing

These skills follow the toolbox maturity lifecycle:
- **sandbox/** — experimental, may break
- **incubating/** — proven useful, being polished (you are here)
- **graduated/** — stable, recommended for all team members

To propose changes, open a PR against the skill's `.md` file. The skill prompt is the entire implementation — there's no code to build or deploy.
