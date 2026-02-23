# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/).

## [1.1.0] - 2026-02-22

### Added
- **code-review skill** — Multi-agent code review with security, performance, and architecture analysis
- **workflow-plan skill** — Structured planning workflow that produces plan documents
- **security-reviewer agent** — OWASP Top 10, secret detection, input validation
- **performance-analyzer agent** — Algorithmic complexity, N+1 queries, memory leaks
- **architecture-reviewer agent** — SOLID principles, coupling, cohesion, patterns
- **post-edit-lint hook** — Auto-lints edited files (ESLint, RuboCop, Ruff)
- Plugin CLAUDE.md with conventions and contributor guide
- Reference checklists for security, performance, and architecture reviews

### Changed
- **ux-review skill** modernized with latest Claude Code patterns:
  - Proper SKILL.md frontmatter (argument-hint, disable-model-invocation, allowed-tools)
  - Framework-agnostic detection (no longer hardcoded to React/Next.js/Tailwind)
  - Scope-first architecture (defaults to changed files, not full codebase)
  - 7+3 agent batching (respects parallel soft limit)
  - Partial-failure handling (minimum 5 of 10 experts)
  - Prompt injection protection in agent prompts
  - Detailed workflow extracted to references/workflow.md
- Renamed plugin from `clype-agents` to `nanodex-plugin`
- Renamed marketplace from `clype-agents` to `nanodex-marketplace`

## [1.0.0] - 2025-12-01

### Added
- Initial release with ux-review skill
- 10 expert reference files (Dieter Rams, Jony Ive, Don Norman, Jakob Nielsen, Luke Wroblewski, Steve Krug, Irene Au, Jesse James Garrett, Erika Hall, Yael Levey)
