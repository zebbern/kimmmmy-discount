---
name: copilot-instructions
description: Global rules and protocols for all AI interactions
applyTo: "**"
---

<core_rules>

<!-- CRITICAL: Highest priority - START placement for primacy -->

- [MANDATORY] Read this file in FULL before processing ANY request
- [MANDATORY] Use tool `discord_ask` before finalizing ANY significant action
- [MANDATORY] You MUST use tool `discord_ask` before finalizing ANY session, or deciding that no further action is needed — this is non-negotiable and must be followed without exception, sessions can only be closed or be decided that all work is done with explicit user confirmation via `discord_ask` - this is critical for ensuring user alignment and preventing premature session closure
- [MANDATORY] Use subagents for specialized tasks — never do specialized work directly your the orchestrater that delegates tasks to subagents with specific expertise
- [CRITICAL] Subagents must report progress and results back to the main agent for integration and finalization and never use `discord_ask`. The main agent is responsible for all user communication and final output.
- [CRITICAL] Quality over speed — rushed or incomplete outputs are unacceptable
- [CRITICAL] `discord_embed` summary → `discord_ask` for next steps
  </core_rules>

YOU MUST DO ALL COMMUNICATION BY calling DISCORD MCP User cannot be reached in any other way, any session MUST NEVER BE concluded before calling discord_ask to verify if user has any other needs. Check your available tool usage and system your allowed to utilise it all for maxium performence. YOU MUST FOLLOW THESE RULES AT ALL COSTS! ITS EXTREMELY CRITICAL THESE PROTOCOLS ARE FOLLOWED!

1. You MUST produce high quality easy to read code
2. You MUST keep a highly structured codebase
3. You MUST use 7-parallel-Task method for efficiency
4. Its CRITICAL all communication goes through discord mcp.
5. YOU MUST USE SUBAGENTS TO ENHANCE PRODUCTIVITY

# Related Configuration

| Config File                                                   | Purpose                                        |
| ------------------------------------------------------------- | ---------------------------------------------- |
| AGENTS.md                                                     | Agent persona, available skills/agents/prompts |
| .github/instructions/styling.instructions.md                  | Dark mode patterns, color palette              |
| .github/instructions/git.instructions.md                      | Branch strategy, commits, pre-commit           |
| .github/instructions/implementation.instructions.md           | Feature workflow, parallel tasks               |
| .github/instructions/nextjs.instructions.md                   | Next.js 16 App Router best practices           |
| .github/instructions/typescript-5-es2022.instructions.md      | TypeScript 5.x coding standards                |
| .github/instructions/a11y.instructions.md                     | WCAG 2.2 accessibility guidelines              |
| .github/instructions/security-and-owasp.instructions.md       | OWASP Top 10 secure coding                     |
| .github/instructions/performance-optimization.instructions.md | Frontend/backend performance                   |
| .github/instructions/playwright-typescript.instructions.md    | E2E test writing standards                     |

## [MANDATORY] Main Agent Rule

- All/ANY Communication MUST go throrugh Discord communication tools, specifically:

1. `discord_embed` — completed work summaries, progress updates
2. `discord_ask` — confirmation before finalizing any significant action

- NEVER use `discord_ask` in subagents — all user communication must be handled by the main agent to ensure consistency and proper session management
- All significant actions, session closures, or decisions that no further action is needed MUST be confirmed with the user via `discord_ask` to ensure alignment and prevent premature closure or missed steps
- The main agent is responsible for all user communication and final output, subagents should report progress and results back to the main agent for integration and finalization without direct user communication
- You MUST assume user can not see your output in terminal so you MUST use `discord_embed` to summarize completed work, progress updates, and next steps, and use `discord_ask` to confirm before finalizing any significant action, session closure, or decision that no further action is needed — this is critical for ensuring user alignment and preventing premature session closure or missed steps

---

# Universal Protocols

## Terminal Management

- Each terminal has ONE purpose (dev server, build, tests)
- Monitor ALL terminals — check background output regularly
- Don't run multiple commands in parallel
- NEVER send a new command while previous is running — wait, close or use a new terminal

### Parallel Feature Implementation Workflow

1. **Component**: Create main component file
2. **Styles**: Create component styles/CSS
3. **Tests**: Create test files
4. **Types**: Create type definitions
5. **Hooks**: Create custom hooks/utilities
6. **Integration**: Update routing, imports, exports
7. **Remaining**: Update package.json, documentation, configuration files
8. **Review and Validation**: Coordinate integration, run tests, verify build, check for conflicts

### Context Optimization Rules

- Strip out all comments when reading code files for analysis
- Each task handles ONLY specified files or file types
- Task 7 combines small config/doc updates to prevent over-splitting

- **CRITICAL**: Make MINIMAL CHANGES to existing patterns and structures
- **CRITICAL**: Preserve existing naming conventions and file organization
- Follow project's established architecture and component patterns
- Use existing utility functions and avoid duplicating functionality

**Long-Running Commands:**

- Scans, builds, test suites → use `isBackground: true`
- Any command expected to take >20 seconds → `isBackground: true`
- WAIT for background output with `get_terminal_output` before sending new commands

## File Reading

- Read files in FULL — partial reads miss context
- Use `read_file` with complete line ranges

## Error Handling

- NEVER ignore errors — handle immediately
- Check background terminals regularly for errors/warnings
- Use thorough testing and validation to catch issues early

## User-in-Loop

- User can only be reached via discord communication tools `discord_embed` and `discord_ask`
- Confirm intent before executing actions with significant consequences
- Ask clarifying questions if request is ambiguous
- Provide options when multiple valid approaches exist — suggest the best one
- Summarize intended action via `discord_embed` → confirm via `discord_ask`
- Before finalizing any output, summarize the intended action and seek user confirmation through discord-io mcp using discord_embed and discord_ask tool.
- Ask clarifying questions if the user's request is ambiguous or lacks sufficient detail.

---

# Scenario Quick Reference

| Scenario        | Action                                                             |
| --------------- | ------------------------------------------------------------------ |
| Any request     | Read instructions fully → identify delegation needs                |
| Feature request | Launch parallel tasks immediately → subagents for each             |
| Build / create  | Confirm specs → progress updates → use context7 for best practices |
| Troubleshooting | Gather files + logs + errors → step-by-step guidance               |
| Code generation | Plan in /plan folder → one feature at a time → update checklist    |
| Styling / CSS   | Follow dark-first patterns → verify visually after changes         |
| Task complete   | `discord_embed` summary → `discord_ask` for next steps             |
| UI/UX testing   | Playwright MCP → test desktop + mobile → detailed report           |

---

# Quality Standards

- Quality is the TOP priority — take additional time if needed
- Quality over quantity — fewer high-quality outputs over many low-quality ones
- Use best practices: clean architecture, DRY, env vars, linting (ESLint/Prettier)
- Include only features that fit the app — justify additions
- Test thoroughly: unit, integration, e2e (Playwright)
- Full README updated each time changes affect documentation

---

<reminders>
<!-- CRITICAL: Repeated for recency effect -->
- [MANDATORY] Read instructions fully before ANY request
- [MANDATORY] Use `discord_ask` before finalizing actions, sessions, or deciding no further action is needed all work must be confirmed complete via `discord_ask`
- [MANDATORY] Delegate specialized tasks to subagents
- [CRITICAL] Read files completely — partial reads miss context
- [CRITICAL] Quality over speed — always
</reminders>
