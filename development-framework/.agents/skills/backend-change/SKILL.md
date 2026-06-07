---
name: backend-change
description: Use this skill only for making changes to backend logic, services, schemas, and database migrations.
---

# Skill: Backend Change

## Purpose
Guide the AI agent in making structured, safe, and backwards-compatible backend code changes, database migrations, or business logic updates.

## When to Use
Use this skill when modifying:
- API endpoints, controllers, routers, or request handlers.
- Database access patterns, models, migrations, or database queries.
- Business services, validation modules, or background jobs.

## Required Documents to Read
- Default: `docs/ai/context.md`
- Conditional:
  - `docs/ai/architecture.md` (for module dependencies and flows)
  - `docs/ai/coding-standards.md` (for backend conventions)
  - `docs/ai/testing-policy.md` (for backend testing instructions)

## Step-by-Step Workflow
1. **Analyze Requirements**: Understand the target feature or behavior adjustment.
2. **Discover Files**: Locate the specific routers, services, entities, or test suites to modify. Inspect related modules.
3. **Draft the Code**: Write clean, modular, and lint-compliant backend code. Ensure any API changes are documented.
4. **Database Migration (if applicable)**:
   - Create a structured migration script following the project's database policy.
   - Write rollback instructions.
5. **Write Unit/Integration Tests**: Add test coverage for any new behavior or modified logic.
6. **Local Validation**: Run the backend unit/integration tests to ensure no regressions are introduced.

## Validation Checklist
- [ ] No compilation/type errors and conforms to coding standards.
- [ ] Added/updated unit and integration tests.
- [ ] Validated database migration scripts and rollback plans.
- [ ] No secrets or environment configurations hardcoded.

## Forbidden Actions
- **No Broad Refactors**: Do not refactor unrelated backend services or controllers.
- **No Direct Schema Updates**: Never bypass migrations to update database structures.

## Final Response Format
Always include:
- Changed files
- What changed in the backend logic
- Tests run
- Tests not run, if any
- Risks
- Rollback notes
