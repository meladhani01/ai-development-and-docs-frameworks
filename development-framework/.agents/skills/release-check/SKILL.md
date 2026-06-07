---
name: release-check
description: Use this skill only for validating release readiness, check env parameters, and running pre-release test checklists.
---

# Skill: Release Check

## Purpose
Confirm the stability, config integrity, and correctness of the codebase before deploying updates to production or staging environments.

## When to Use
Use this skill when:
- Evaluating release readiness.
- Checking environment variable templates or configurations.
- Auditing release scripts, CI/CD configs, or Docker assets.

## Required Documents to Read
- Default: `docs/ai/context.md`
- Conditional:
  - `docs/ai/release-policy.md` (for release checklists and guidelines)
  - `docs/ai/security-policy.md` (for configuration safety checks)

## Step-by-Step Workflow
1. **Auditing Changes**: Identify the updates since the last release tag.
2. **Review Config Templates**: Verify that new configurations have placeholders in `.env.example`.
3. **Validate Database Migrations**: Ensure migration files parse correctly and include verified rollbacks.
4. **Execute Release Suite**: Run full end-to-end integration and security test suites.
5. **Verify Rollback & Monitoring Plans**: Confirm rollback procedures and logging paths are active and clear.

## Validation Checklist
- [ ] No compilation/type issues.
- [ ] All unit, integration, and E2E tests pass.
- [ ] Database migrations have valid rollback notes.
- [ ] Environment variable changes are documented in `.env.example`.

## Forbidden Actions
- **No Manual Hotfixes**: Do not modify production configurations or hotfix code on the server directly. All fixes must go through the standard PR workflow.

## Final Response Format
Always include:
- Changed files (e.g., config templates, scripts)
- Release verification status
- Migration & rollback validation status
- Risks identified
- Rollback execution instructions
