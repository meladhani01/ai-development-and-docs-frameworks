---
name: bug-fix
description: Use this skill only for troubleshooting, identifying root causes, and applying minimal patches to fix bugs.
---

# Skill: Bug Fix

## Purpose
Guide the AI agent through diagnosing code bugs, writing regression tests, and implementing precise, minimal fixes.

## When to Use
Use this skill when:
- Resolving compiler errors, runtime exceptions, or failing tests.
- Troubleshooting unexpected system behavior, performance bottlenecks, or logic flaws.

## Required Documents to Read
- Default: `docs/ai/context.md`
- Conditional:
  - `docs/ai/testing-policy.md` (for setting up regression tests)
  - `docs/ai/glossary.md` (for domain jargon and terms)

## Step-by-Step Workflow
1. **Replicate the Bug**: Create a unit test or run a command sequence that consistently triggers the issue.
2. **Trace the Bug**: Walk through the logs, stack trace, variables, and code paths to isolate the root cause.
3. **Draft the Patch**: Implement the smallest possible change that resolves the bug without side effects.
4. **Write Regression Tests**: Ensure the replicated unit test is checked in to prevent the bug from returning.
5. **Verify Fix**: Run full test suites locally to ensure no other logic is broken by the fix.

## Validation Checklist
- [ ] Fixes the target bug consistently.
- [ ] Added regression tests covering the fix.
- [ ] No unrelated files or code structures modified.
- [ ] Code passes standard linters and typecheck.

## Forbidden Actions
- **No Refactoring**: Do not clean up code or restructure files while applying a bug fix. Focus exclusively on fixing the issue.

## Final Response Format
Always include:
- Changed files
- Root cause identified
- Solution implemented
- Regression tests added
- Rollback notes
