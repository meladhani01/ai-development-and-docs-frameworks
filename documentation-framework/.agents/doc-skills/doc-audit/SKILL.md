---
name: doc-audit
description: Use this skill only for auditing existing documentation files, finding broken paths, identifying style discrepancies, and checking code snippet syntax.
---

# Skill: Documentation Audit & Fix

## Purpose
Maintain the quality, health, and correctness of the project's documentation repository by auditing files for style, links, formatting, and outdated code.

## When to Use
Use this skill when:
- Reviewing documentation updates in a Pull Request.
- Conducting periodic documentation quality audits.
- Fixing broken relative links, typos, and markdown lint errors.

## Required Documents to Read
- Default: `docs/ai-docs/context.md`
- Conditional:
  - `docs/ai-docs/style-guide.md` (for checking formatting and visual guidelines)
  - `docs/ai-docs/review-policy.md` (for the review checklist and response format)

## Step-by-Step Workflow

1. **Target Identification**: List the specific documentation files or directories to be audited.
2. **Execute Link Audits**:
   - Check every relative Markdown file path (e.g., `[Title](../path/to/file.md)`). Verify that the path points to an actual file.
   - Check header anchor links (e.g., `[Go](#go-to-step)`) to ensure they match target titles in the file.
3. **Execute Style and Grammar Checks**:
   - Verify headings nest correctly and follow sentence-casing.
   - Search for unfinished placeholders (e.g., `TODO`, `TBD`, `TODO_PLACEHOLDER`).
   - Check that inline files and symbols are properly formatted without backticks inside links.
4. **Compile Snippet Audit**:
   - Verify that code blocks are closed, syntax-highlighted, and use up-to-date syntax matching the production code.
5. **Report and Rectify**:
   - Format the findings according to the review output structure in [review-policy.md](file:///d:/Copto/ai-assisted-development-framework/documentation-framework/docs/ai-docs/review-policy.md).
   - If requested, fix syntax, formatting, link bugs, and typos immediately.

## Validation Checklist
- [ ] No broken relative paths in the audited pages.
- [ ] Mapped and reported all formatting/lint errors.
- [ ] Verified that code blocks match the current main branch implementation.
- [ ] Compiled findings in the required format.

## Forbidden Actions
- **No Arbitrary Rewrites**: Do not change the voice or structure of a document during a link audit unless style guide compliance requires it. Keep changes minimal.

## Final Response Format
Format your output according to the `Review Output Format` section in [review-policy.md](file:///d:/Copto/ai-assisted-development-framework/documentation-framework/docs/ai-docs/review-policy.md).
