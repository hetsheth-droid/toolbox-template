# toolbox

A shared monorepo for tools, skills, and scripts across your team. Everything here is built by the team, for the team — from quick shell scripts to full onboarding systems.

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

## Quick start

### Using this template

1. Click **"Use this template"** on GitHub (or clone this repo)
2. Start adding tools to `sandbox/`
3. Promote them as they mature

### Add a new tool

1. Create a directory under `sandbox/` with your tool name
2. Add a `README.md` — what it does, how to run it, who to ask
3. Open a PR (no approval needed for sandbox, but PRs go through for visibility)

### Promote a tool

Open a PR that moves the directory up a tier. See [CONTRIBUTING.md](CONTRIBUTING.md) for the full requirements at each level.

### Retire a tool

Open a PR to delete it. Note in the PR why and what replaces it (if anything).

## Resources

- [**The Complete Guide to Building Skills for Claude**](resources/complete-guide-to-building-skills-for-claude.pdf) — Anthropic's 32-page playbook covering skill fundamentals, planning, testing, distribution, and design patterns
- [obra/superpowers](https://github.com/obra/superpowers) — upstream repo for the superpowers skills framework
- [garrytan/gstack](https://github.com/garrytan/gstack) — upstream repo for gstack
- [anthropics/skills](https://github.com/anthropics/skills) — Anthropic's official skills repo (skill-creator + 16 other skills)
