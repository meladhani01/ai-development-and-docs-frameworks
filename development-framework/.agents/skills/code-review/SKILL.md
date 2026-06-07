---
name: code-review
description: Use this skill only for auditing Pull Requests, reviewing code updates, and highlighting design flaws or security vulnerabilities.
---

# Skill: Code Review

## Purpose
Ensure all code contributions conform to the repository's security, architectural, data scoping, and testing quality guidelines.

## When to Use
Use this skill when:
- Reviewing Git diffs, PR branches, or specific commits.
- Evaluating a proposed implementation plan.

## Required Documents to Read
- Default: `docs/ai/context.md`
- Conditional:
  - `docs/ai/code-review.md` (for the PR review response format)
  - `docs/ai/security-policy.md` (for permissions and data scope rules)

## Step-by-Step Workflow
1. **Analyze Diff Scope**: Identify what files were added, modified, or deleted.
2. **Verify Correctness**: Check for logical bugs, edge cases, and off-by-one errors.
3. **Audit Security & Scope**:
   - Check if database queries respect tenant isolation boundaries.
   - Verify that routes enforce correct guards and authorization checks.
   - Look for hardcoded credentials or sensitive data leaks.
4. **Evaluate Testing**: Confirm that sufficient unit and integration test coverage exists.
5. **Generate Response**: Construct the review feedback according to the format in [code-review.md](file:///d:/Copto/ai-assisted-development-framework/development-framework/docs/ai/code-review.md).

## Validation Checklist
- [ ] Checked for security loopholes and data scoping leaks.
- [ ] Confirmed appropriate tests are present.
- [ ] Verified database migrations have rollbacks.
- [ ] Feedback is formatted in the required structure.

## Forbidden Actions
- **No Subjective Style Arguing**: Focus on bugs, security, performance, and correctness, not styling preferences that are not covered by the style guide.

## Final Response Format
Format review feedback according to the structure in [code-review.md](file:///d:/Copto/ai-assisted-development-framework/development-framework/docs/ai/code-review.md).
