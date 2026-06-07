# Review AI Documentation Framework Prompt

Use this prompt after the AI Documentation Framework files are generated in a target repository.

---

Review the AI Documentation Framework files you just created.

Check specifically:

1. `AGENTS.md` does NOT instruct the AI to read all documentation guidelines every time.
2. `CLAUDE.md` does NOT import all docs by default and references `@docs/ai-docs/context.md` as the main entry point.
3. `GEMINI.md` does NOT load all docs by default and directs the model to start with `docs/ai-docs/context.md`.
4. `docs/ai-docs/context.md` is the only always-read shared context file.
5. Other documents (style-guide, templates, review-policy, glossary) are read conditionally depending on the task type.
6. Skills are correctly structured under `.agents/doc-skills/`.
7. Every skill `SKILL.md` file starts with the required `name` and `description` metadata frontmatter block.
8. Every skill instructs the agent to inspect only relevant files and nearby code, avoiding broad codebase scans.
9. The project archetype is correctly identified and selected (SaaS/Web, CLI, Library/SDK, Data/ML, Embedded) and referenced throughout the templates.
10. No secrets, private credentials, or customer PII are present in any files or snippet examples.
11. All internal relative paths and header anchor cross-links are valid and exist in the directory.
12. Any unverified or placeholder items are explicitly marked as `TBD - needs team confirmation`.

If anything is wrong, fix only the AI documentation framework files.

Then summarize:

- Files updated
- Token-efficiency improvements
- Domain-specific customization details (archetypes verified)
- Remaining TBD items
- Items needing Tech Lead review
