# Gemini instructions (Documentation)

This repository uses a repo-based AI Documentation Framework.

Default project context:

- Read `docs/ai-docs/context.md`

Do not read all AI documentation guidelines by default. Read additional files only when the task requires them.

Conditional docs:

- Styles, formatting, layouts, diagrams → `docs/ai-docs/style-guide.md`
- Templates (Tutorials, APIs, Concept Guides) → `docs/ai-docs/content-types.md`
- Link validation, review checks, code snippet testing → `docs/ai-docs/review-policy.md`
- Unclear jargon or product terminology → `docs/ai-docs/glossary.md`

Use only the relevant workflow:

- API & Reference Documentation → `.agents/doc-skills/api-documentation/SKILL.md`
- Tutorial & Guide Creation → `.agents/doc-skills/tutorial-writing/SKILL.md`
- Architecture Explanation → `.agents/doc-skills/architecture-explanation/SKILL.md`
- Documentation Audit & Fix → `.agents/doc-skills/doc-audit/SKILL.md`
- Release Walkthrough & Changelog → `.agents/doc-skills/release-walkthrough/SKILL.md`

Rules:

- Do not perform a full codebase scan unless explicitly required.
- Inspect only the relevant documentation folders and nearby source code.
- Make the smallest safe edit.
- Follow the project's documentation style guide.
- Do not invent project features or parameters. Only document existing logic.
- Do not expose secrets, credentials, tokens, or private customer data.

Final response must include created or modified files, changes made, checks performed, assumptions/TBDs, and risks.
