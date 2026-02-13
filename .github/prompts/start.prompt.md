---
name: start
description: Initialize a new chat session with full project context. Use at the start of every conversation.
---

# Session Initialization

You are starting a new session with zero context. Follow these steps IN ORDER to build deep understanding before doing any work. YOU MUST DO ALL COMMUNICATION BY calling DISCORD MCP User cannot be reached in any other way, any session MUST NEVER BE concluded before calling discord_ask to verify if user has any other needs. Check your available tool usage and system your allowed to utilise it all for maxium performence. YOU MUST FOLLOW THESE RULES AT ALL COSTS! ITS EXTREMELY CRITICAL THESE PROTOCOLS ARE FOLLOWED!

1. You MUST produce high quality easy to read code
2. You MUST keep a highly structured codebase
3. You MUST use 7-parallel-Task method for efficiency
4. Its CRITICAL all communication goes through discord mcp.
5. YOU MUST USE SUBAGENTS TO ENHANCE PRODUCTIVITY

## Step 1: Read Core Instructions

Read these files completely — every line:

1. [AGENTS.md](../../AGENTS.md) — your role, available skills, tech stack
2. [.github/copilot-instructions.md](../copilot-instructions.md) — global rules and protocols for all AI interactions THIS MUST BE READ IN FULL AND UNDERSTOOD BEFORE ANY ACTIONS ARE TAKEN file is 140 lines that set critical rules for all interactions
3. [.github/instructions/styling.instructions.md](../instructions/styling.instructions.md) — dark-first CSS patterns
4. [.github/instructions/git.instructions.md](../instructions/git.instructions.md) — commit and staging rules
5. [.github/instructions/implementation.instructions.md](../instructions/implementation.instructions.md) — feature workflow

## Step 2: Understand Project Structure

Run these to map the codebase:

1. List the root directory to understand the project layout
2. Read `package.json` to understand dependencies, scripts, and framework
3. Read `tsconfig.json` to understand TypeScript configuration
4. If `next.config.*` exists, read it for Next.js setup
5. If `tailwind.config.*` exists, read it for styling configuration
6. Explore `src/` or `app/` or `docs/` if available or other important directories to understand the component architecture

## Step 3: Identify Patterns

Look for and internalize:

- **Naming conventions** — file names, component names, variable naming
- **Folder structure** — how features/pages/components are organized
- **Import patterns** — barrel files, path aliases, relative vs absolute
- **State management** — RSC vs client components, data fetching patterns
- **Styling approach** — Tailwind classes, CSS modules, inline styles

## Step 4: Confirm Readiness

After completing steps 1-3, provide a brief summary:

1. **Tech stack** identified (framework, styling, testing)
2. **Project structure** understood (key directories and their purposes)
3. **Conventions** observed (naming, patterns, architecture)
4. **Rules loaded** (confirm all instruction files were read)

Then ask the user what they'd like to work on.

## Important Reminders

- Quality over speed — take time to understand before acting
- Follow the dark-first styling rules without exception
- Use context7 MCP for up-to-date framework documentation
- Use `discord_ask` before finalizing significant actions

## [MANDATORY] Main Agent Rule

- All/ANY Communication MUST go throrugh Discord communication tools, specifically:

1. `discord_embed` — completed work summaries, progress updates
2. `discord_ask` — confirmation before finalizing any significant action

- NEVER use `discord_ask` in subagents — all user communication must be handled by the main agent to ensure consistency and proper session management
- All significant actions, session closures, or decisions that no further action is needed MUST be confirmed with the user via `discord_ask` to ensure alignment and prevent premature closure or missed steps
- The main agent is responsible for all user communication and final output, subagents should report progress and results back to the main agent for integration and finalization without direct user communication
- You MUST assume user can not see your output in terminal so you MUST use `discord_embed` to summarize completed work, progress updates, and next steps, and use `discord_ask` to confirm before finalizing any significant action, session closure, or decision that no further action is needed — this is critical for ensuring user alignment and preventing premature session closure or missed steps
