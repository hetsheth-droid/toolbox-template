# Toolbox — Agent Instructions

This is a shared monorepo for tools, skills, and scripts. It uses a maturity model to organize tools by stability.

## Repository structure

```
toolbox/
  sandbox/          # experimental, minimal bar (just a README)
  incubating/       # team-adopted, documented, tested
  graduated/        # production-grade, stable API
  resources/        # reference materials (PDFs, guides)
```

## Bundled skill packs

Three community skill packs are included in `incubating/`:

- **superpowers** (`incubating/superpowers-skills/`) — agentic skills framework by obra. TDD, debugging, code review, subagents, worktrees. Install via `/plugin install superpowers@claude-plugins-official` or symlink.
- **gstack** (`incubating/gstack/`) — 23-tool engineering skill pack by Garry Tan. Run `cd incubating/gstack && ./setup` to install. Requires Bun v1.0+.
- **skill-creator** (`incubating/skill-creator/`) — Anthropic's official skill for building new skills, running evals, and optimizing triggering.

Two standalone skills:

- **/journey-note** (`incubating/skills/journey-note/`) — generates narrative session summaries
- **/ship** (`incubating/skills/ship/`) — one-command commit, push, and PR with journey note linking

## Conventions

### Adding a new tool

1. Create a directory under `sandbox/` with a descriptive name
2. Add a `README.md` explaining what it does, how to run it, and who to ask
3. Open a PR — lightweight review for sandbox tier

### Git workflow

- Never push directly to main — always create a branch and PR
- Use conventional commit prefixes: `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`
- Keep commit subject lines under 72 characters, imperative mood

### Promoting a tool

- **Sandbox → Incubating:** At least one team actively using it, has documentation and some tests
- **Incubating → Graduated:** Used across multiple teams, comprehensive tests, stable interface

### Skill files

Skills are `.md` files (either `SKILL.md` or `<name>.md`) that teach Claude Code how to perform workflows. They are not executable code — they are prompt specifications. To install a skill, copy or symlink its `.md` file to `~/.claude/commands/` (global) or `.claude/commands/` (per-project).

## Resources

- `resources/complete-guide-to-building-skills-for-claude.pdf` — Anthropic's 32-page skills playbook
- Upstream repos: [obra/superpowers](https://github.com/obra/superpowers), [garrytan/gstack](https://github.com/garrytan/gstack), [anthropics/skills](https://github.com/anthropics/skills)
