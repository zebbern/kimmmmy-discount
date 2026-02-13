---
name: git-workflow
description: Git commit conventions, branch strategy, and pre-commit requirements
applyTo: "**"
---

<core_rules>

- [MANDATORY] All work on `main` branch
- [MANDATORY] Conventional Commits format for all commit messages
- [CRITICAL] Never commit sensitive files or auto-generated artifacts
  </core_rules>

---

# Commit Message Format

Use [Conventional Commits](https://www.conventionalcommits.org/):

| Prefix      | Use For                 |
| ----------- | ----------------------- |
| `feat:`     | New features            |
| `fix:`      | Bug fixes               |
| `chore:`    | Maintenance / cleanup   |
| `refactor:` | Code restructuring      |
| `test:`     | Adding / updating tests |
| `docs:`     | Documentation changes   |

---

# Staging Rules

- Run `git status` first — review what's changed
- Stage selectively — only source code changes
- Push: `git push origin main` 

## Never Commit

| Pattern             | Reason                       |
| ------------------- | ---------------------------- |
| `.env*`             | Secrets / credentials        |
| `node_modules/`     | Dependencies — use lockfile  |
| `coverage/`         | Generated test coverage      |
| `.playwright-mcp/`  | Playwright artifacts         |
| `build/` / `dist/`  | Build artifacts              |
| `package-lock.json` | Auto-generated (review only) |
| `.vscode/`          | Editor-specific config       |

---

<reminders>
- [MANDATORY] Conventional Commits format — always
- [MANDATORY] Always review `git status` before staging
- [CRITICAL] Stage only source code changes — no auto-generated files
- [CRITICAL] Never commit .env files, node_modules, or build artifacts
</reminders>
