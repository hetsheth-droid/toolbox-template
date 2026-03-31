# toolbox

A shared monorepo for tools, skills, and scripts across your team. Everything here is built by the team, for the team — from quick shell scripts to full onboarding systems.

This template comes pre-loaded with battle-tested Claude Code skills and a maturity model for organizing your tools as they grow.

## Getting started

### 1. Create your repo from this template

Click **"Use this template"** on GitHub → **"Create a new repository"**. Name it whatever you want (e.g., `my-team-toolbox`). Then clone it:

```bash
git clone https://github.com/<your-org>/my-team-toolbox.git
cd my-team-toolbox
```

### 2. Install the bundled skills

This template comes with three skill packs and two standalone skills. Install whichever you want:

#### Superpowers (TDD, debugging, code review, subagents)

The easiest way — install via Claude Code plugin marketplace:

```bash
/plugin install superpowers@claude-plugins-official
```

Or symlink from this repo for manual control:

```bash
ln -s "$(pwd)/incubating/superpowers-skills" ~/.claude/skills/superpowers
```

See [incubating/superpowers-skills/UPSTREAM-README.md](incubating/superpowers-skills/UPSTREAM-README.md) for full docs.

#### gstack (23-tool engineering skill pack)

```bash
cd incubating/gstack && ./setup
```

This registers all gstack skills globally. Available commands include `/office-hours`, `/plan-ceo-review`, `/review`, `/qa`, `/ship`, `/investigate`, `/browse`, and more.

See [incubating/gstack/README.md](incubating/gstack/README.md) for full docs. Requires [Bun](https://bun.sh/) v1.0+.

#### Skill Creator (build your own skills)

No installation needed — just tell Claude Code:

```
Use the skill-creator at incubating/skill-creator/SKILL.md to help me build a new skill
```

Or copy it to your commands directory:

```bash
cp incubating/skill-creator/SKILL.md ~/.claude/commands/skill-creator.md
```

#### /journey-note and /ship (session summaries + one-command PRs)

```bash
mkdir -p ~/.claude/commands
cp incubating/skills/journey-note/journey-note.md ~/.claude/commands/journey-note.md
cp incubating/skills/ship/ship.md ~/.claude/commands/ship.md
```

Then use `/journey-note` to capture session summaries and `/ship` to commit, push, and create a PR in one command. `/ship` automatically links today's journey note in the PR description.

See [incubating/skills/README.md](incubating/skills/README.md) for symlink setup and per-project installation.

### 3. Start adding your own tools

Add tools to `sandbox/` — each in its own directory with a README:

```bash
mkdir sandbox/my-tool
echo "# my-tool\n\nWhat it does and how to use it." > sandbox/my-tool/README.md
```

Open a PR and you're done.

## What's in here

### Incubating — team-adopted, documented, tested

| Tool | What it does | Source |
|------|-------------|--------|
| [**superpowers**](incubating/superpowers-skills/) | Agentic skills framework — TDD, debugging, code review, subagents, worktrees, and more | [obra/superpowers](https://github.com/obra/superpowers) |
| [**gstack**](incubating/gstack/) | 23-tool skill pack — CEO, Designer, Eng Manager, Release Manager, QA roles | [garrytan/gstack](https://github.com/garrytan/gstack) |
| [**skill-creator**](incubating/skill-creator/) | Build new Claude Code skills from scratch, run evals, optimize triggering | [anthropics/skills](https://github.com/anthropics/skills) |
| [**/journey-note**](incubating/skills/journey-note/) | Generates narrative session summaries capturing the intellectual arc of a working session | Original |
| [**/ship**](incubating/skills/ship/) | One-command commit, push, and PR workflow with automatic journey note linking | Original |

### Sandbox — experimental, early-stage

Empty — add your first tool here!

### Graduated — production-grade, stable

None yet. Tools promote here once they're widely used, fully tested, and have a stable interface.

## Maturity model

Inspired by [CNCF project maturity levels](https://www.cncf.io/project-metrics/):

| Tier | Bar | Review |
|------|-----|--------|
| **Sandbox** | Has a README | 1 lightweight approval |
| **Incubating** | Used by a team, has docs + tests | 1 approval |
| **Graduated** | Cross-team use, comprehensive tests, stable API | 1 approval + broader review |

Tools start in `sandbox/` and get promoted via PR as they mature.

## Adding, promoting, and retiring tools

- **Add:** Create a directory under `sandbox/` with a README, open a PR
- **Promote:** Move the directory up a tier via PR. See [CONTRIBUTING.md](CONTRIBUTING.md) for requirements
- **Retire:** Delete via PR, note why and what replaces it

## Resources

- [**The Complete Guide to Building Skills for Claude**](resources/complete-guide-to-building-skills-for-claude.pdf) — Anthropic's 32-page playbook covering skill fundamentals, planning, testing, distribution, and design patterns
- [obra/superpowers](https://github.com/obra/superpowers) — upstream repo for the superpowers skills framework
- [garrytan/gstack](https://github.com/garrytan/gstack) — upstream repo for gstack
- [anthropics/skills](https://github.com/anthropics/skills) — Anthropic's official skills repo (skill-creator + 16 other skills)
- [Claude Code docs](https://docs.anthropic.com/en/docs/claude-code) — official documentation for Claude Code
