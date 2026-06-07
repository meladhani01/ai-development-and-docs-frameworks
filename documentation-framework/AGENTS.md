# Project AI Documentation Instructions

This repository uses a repo-based AI Documentation Framework.

AI tools must keep documentation clear, accurate, consistent, and structured, following the project's style standards.

## Default Reading

Before any documentation changes, read:

- `docs/ai-docs/context.md`

Do not read all AI documentation guidelines by default.

Read extra docs only when relevant:

- Styles, styling conventions, alerts, layouts, diagrams → `docs/ai-docs/style-guide.md`
- Document templates (Tutorials, How-Tos, API reference, explanation guides) → `docs/ai-docs/content-types.md`
- Link validation, correctness review, snippet validation → `docs/ai-docs/review-policy.md`
- Unclear domain terms and glossary definitions → `docs/ai-docs/glossary.md`

## Skills

Use only the relevant documentation skill:

- API Documentation → `.agents/doc-skills/api-documentation/SKILL.md`
- Tutorial & Guide Creation → `.agents/doc-skills/tutorial-writing/SKILL.md`
- Architecture Explanation → `.agents/doc-skills/architecture-explanation/SKILL.md`
- Documentation Audit & Fix → `.agents/doc-skills/doc-audit/SKILL.md`
- Release Walkthrough & Changelog → `.agents/doc-skills/release-walkthrough/SKILL.md`

## Work Rules

- **Strict Source of Truth**: Document only actual implemented features and verified code behavior. Never invent APIs, features, parameters, or configurations.
- **Minimal Localized Edits**: Prefer editing specific sections or paragraphs rather than rewriting whole files, unless a new document is requested.
- **Maintain Consistency**: Follow the tone, voice, structure, and formatting guidelines specified in the style guide.
- **Secrets & PII Protection**: Never include secrets, API keys, passwords, credentials, or actual customer PII in text or code examples. Always use standard placeholders (e.g., `your-api-key`, `user@example.com`).
- **Path and Link Integrity**: Ensure all Markdown cross-links and file links are correct and point to valid files within the repo or correct external URLs.
- **Snippets Accuracy**: Verify that code snippets, commands, and configuration snippets in the documentation match the codebase and run/parse correctly.

## Verification

When documentation changes:

- Verify that all relative links point to existing files.
- Run any markdown/link linter if available.
- Ensure that code snippets match current code signatures.
- Highlight any assumptions or unconfirmed features as `TBD - needs team confirmation`.

## Final Response

Always include:

- Created or modified files
- What changed in the documentation
- Checks performed (link checks, lints, snippet validations)
- Assumptions or TBD items
- Risks or potential impact (e.g., impact on user onboarding, deprecations)
