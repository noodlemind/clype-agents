# nanodex-marketplace

Expert-driven skills, agents, and hooks for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## Install

```bash
claude plugin marketplace add noodlemind/nanodex-marketplace
claude plugin install nanodex-plugin
```

## Skills

### `/nanodex:ux-review`

A 10-expert UI/UX review panel. Spawns parallel sub-agents — each embodying a world-class designer — to independently audit your interface.

**Experts:** Dieter Rams, Jony Ive, Don Norman, Jakob Nielsen, Luke Wroblewski, Steve Krug, Irene Au, Jesse James Garrett, Erika Hall, Yael Levey.

**Triggers:** "review UX", "UX audit", "design review", "polish the UI", "streamline the interface"

**What it does:**
- Scopes review to changed files by default (or specify a page/component)
- Spawns 10 expert agents in two rounds (7 + 3)
- Synthesizes and deduplicates findings with consensus weighting
- Presents a prioritized report (high/medium/low impact)
- Applies selected fixes while preserving your visual theme

### `/nanodex:code-review`

A multi-agent code review panel with security, performance, and architecture reviewers.

**Triggers:** "review code", "code review", "check code quality", "audit the code"

**What it does:**
- Scopes review to changed files, specific paths, or a PR number
- Spawns 3 specialized agents in parallel (security, performance, architecture)
- Checks plan compliance if a plan document exists in `docs/plans/`
- Synthesizes findings into a prioritized report with concrete fixes

### `/nanodex:workflow-plan`

Creates structured implementation plans from feature descriptions.

**What it does:**
- Explores the codebase for patterns and conventions
- Produces a detailed plan document in `docs/plans/`
- Works both interactively and when orchestrated by other agents

## Agents

| Agent | Focus | Tools |
|-------|-------|-------|
| `security-reviewer` | OWASP Top 10, secrets, injection, auth | Read, Grep, Glob |
| `performance-analyzer` | Complexity, N+1 queries, memory, bundles | Read, Grep, Glob |
| `architecture-reviewer` | SOLID, coupling, cohesion, patterns | Read, Grep, Glob |

## Hooks

### post-edit-lint

Fires after every `Edit`, `Write`, or `MultiEdit` operation. Detects the project's linter (ESLint, RuboCop, or Ruff) and runs it on the edited file.

## License

MIT
