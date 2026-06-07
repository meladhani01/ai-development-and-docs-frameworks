---
name: frontend-change
description: Use this skill only for modifying UI components, pages, styles, routing, assets, or frontend state management.
---

# Skill: Frontend Change

## Purpose
Guide the AI agent in building responsive, high-fidelity, and state-of-the-art frontend interfaces, layouts, or component assets.

## When to Use
Use this skill when modifying:
- UI pages, routing, navigation, or layouts.
- Component designs, styles, assets, or animations.
- Frontend state management, API client integrations, or client-side form validations.

## Required Documents to Read
- Default: `docs/ai/context.md`
- Conditional:
  - `docs/ai/coding-standards.md` (for frontend UI and styling guidelines)
  - `docs/ai/testing-policy.md` (for Cypress, Playwright, Jest, or component tests)

## Step-by-Step Workflow
1. **Analyze UX/UI Design**: Understand the layout grid, typography, colors, and user interactions required.
2. **Component Separation**: Write modular, reusable, and responsive components.
3. **Styling and Theme Integration**: Follow CSS/Tailwind design tokens and standard variables.
4. **State & API Handling**: Hook up event handlers, client validation logic, and server communications.
5. **Local Validation**: Run local development builds and execute component or E2E tests.

## Validation Checklist
- [ ] Conforms to design layout and is fully responsive (mobile, tablet, desktop).
- [ ] No compilation/TypeScript errors.
- [ ] Verified API payloads and state management integrations.
- [ ] Run linting and unit/E2E UI test suites.

## Forbidden Actions
- **No Ad-Hoc Styling**: Do not bypass style systems or themes. Use design tokens.
- **No Mock APIs**: Ensure server integrations hook up correctly and are not left mocked in production.

## Final Response Format
Always include:
- Changed files
- What changed in the UI and layout
- Tests run (E2E, component, build check)
- Risks
- Rollback notes
