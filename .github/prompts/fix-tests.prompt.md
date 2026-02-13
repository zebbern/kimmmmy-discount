---
name: fix-tests
description: Diagnose and fix failing tests by analyzing errors, reading source code, and applying fixes
---

# Fix Failing Tests

Diagnose and fix test failures systematically.

## Step 1: Identify Failures

Run the test suite:

```bash
npx vitest run 2>&1 | tail -100
```

If specific test files are mentioned, run those:

```bash
npx vitest run path/to/test.test.tsx
```

## Step 2: Analyze Each Failure

For each failing test:

1. **Read the full error** — stack trace, assertion message, expected vs received
2. **Read the test file** — understand what the test expects
3. **Read the source file** — understand what the code actually does
4. **Identify root cause** — is it the test or the source that's wrong?

## Step 3: Classify the Issue

| Category      | Fix Target  | Example                                  |
| ------------- | ----------- | ---------------------------------------- |
| Stale test    | Test file   | Test expects old behavior after refactor |
| Bug in source | Source file | Code doesn't match intended behavior     |
| Missing mock  | Test file   | External dependency not mocked           |
| Type error    | Either      | TypeScript type mismatch                 |
| Import error  | Either      | Module not found or circular import      |
| Async issue   | Test file   | Missing `await` or `waitFor`             |

## Step 4: Apply Fixes

- Fix one test at a time
- Re-run after each fix to confirm
- If fixing source code, ensure other tests still pass
- Run full suite at the end: `npx vitest run`

## Step 5: Verify

```bash
npx vitest run && npx tsc --noEmit
```

Both must pass with zero errors before reporting completion.
