---
name: implementation-workflow
description: Feature implementation patterns, parallel task strategy, and code generation rules
applyTo: "**/*.{ts,tsx,js,jsx}"
---

<core_rules>

- [MANDATORY] Launch parallel tasks IMMEDIATELY on feature requests — no clarification unless critical
- [MANDATORY] Use subagents for each task to ensure focus and quality
- [CRITICAL] Make MINIMAL changes to existing patterns and structures
- [CRITICAL] Preserve existing naming conventions and file organization
  </core_rules>

---

# Parallel Feature Implementation

Launch these 7 tasks in parallel for every feature:

| Task           | Scope                                   |
| -------------- | --------------------------------------- |
| 1. Component   | Create main component file              |
| 2. Styles      | Create component styles / CSS           |
| 3. Tests       | Create test files (unit + integration)  |
| 4. Types       | Create type definitions                 |
| 5. Hooks       | Create custom hooks / utilities         |
| 6. Integration | Update routing, imports, exports        |
| 7. Config      | Update package.json, docs, config files |

**After all tasks:** Review + Validate → coordinate integration, run tests, verify build, check conflicts.

---

# Code Generation Protocol

1. Craft plan in `/plan` folder with task checklist: `[ ] Task x: Description`
2. Share plan via `discord_embed` → confirm via `discord_ask`
3. One feature at a time — complete X before starting Y
4. Mark `[x]` in checklist when each task is verified
5. Return to plan and update after each task completion

---

# Context Optimization

- Strip comments when reading code files for analysis
- Each task handles ONLY its specified files or file types
- Task 7 combines small config/doc updates to prevent over-splitting
- Use context7 MCP for best practices and up-to-date documentation

---

# Architecture Rules

| Rule              | Details                                                           |
| ----------------- | ----------------------------------------------------------------- |
| Existing patterns | Follow project's established architecture and component patterns  |
| Utilities         | Use existing utility functions — avoid duplicating functionality  |
| Dependencies      | Only add dependencies that fit the app — justify additions        |
| Clean code        | DRY, env vars for config, ESLint/Prettier enforced                |
| Testing           | Unit, integration, e2e (Playwright) — all features must be tested |

---

<reminders>
- [MANDATORY] Parallel 7-task method for feature implementation
- [MANDATORY] Plan in /plan folder → discord_embed → discord_ask before starting
- [CRITICAL] Minimal changes to existing patterns — preserve conventions
- [CRITICAL] One feature at a time — verify before moving on
</reminders>
