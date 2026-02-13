---
name: code-review
description: Run a structured code review checking quality, performance, accessibility, and security
---

# Structured Code Review

Perform a thorough code review on the specified files or recent changes.

## What to Review

If no files specified, check `git diff` for recent changes. Otherwise review the files the user provides.

## Review Checklist

### 1. Correctness

- [ ] Logic is correct and handles edge cases
- [ ] TypeScript types are accurate and strict (no `any`)
- [ ] Error states are handled gracefully
- [ ] Null/undefined checks where needed

### 2. Performance (Reference: `.github/skills/react-best-practices/`)

- [ ] No waterfall fetches — parallel where possible
- [ ] No unnecessary re-renders — proper memoization
- [ ] Bundle impact considered — dynamic imports for heavy deps
- [ ] Server Components used where possible

### 3. Architecture (Reference: `.github/skills/composition-patterns/`)

- [ ] No boolean prop proliferation
- [ ] Composition over configuration
- [ ] Single responsibility per component
- [ ] DRY — no duplicated logic

### 4. Styling

- [ ] Dark-first design followed (no `dark:` prefix reliance)
- [ ] Color palette from styling instructions used
- [ ] Responsive across viewports
- [ ] Accessible contrast ratios

### 5. Security

- [ ] No hardcoded secrets or credentials
- [ ] User input sanitized
- [ ] Server actions authenticated
- [ ] Environment variables used for config

### 6. Testing

- [ ] Tests exist for new/changed code
- [ ] Edge cases covered
- [ ] Tests are meaningful (not just snapshot-only)

## Output Format

For each finding:

```
[SEVERITY] file:line — description
  Suggestion: how to fix
```

Severity levels: `CRITICAL` | `HIGH` | `MEDIUM` | `LOW`

Summarize with counts per severity at the end.
