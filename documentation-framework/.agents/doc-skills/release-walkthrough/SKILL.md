---
name: release-walkthrough
description: Use this skill only for writing changelogs, release notes, upgrade guides, and feature walk-throughs for new code updates.
---

# Skill: Release Walkthrough & Changelog

## Purpose
Document codebase updates, new features, and upgrade instructions in a structured format (Changelog, Release Notes, Upgrade Guide) for developers and end-users.

## When to Use
Use this skill when:
- Creating changelog entries for a new repository release.
- Writing upgrade guides detailing breaking changes, API deprecations, or database migrations.
- Summarizing new feature implementations for user guides.

## Required Documents to Read
- Default: `docs/ai-docs/context.md`
- Conditional:
  - `docs/ai-docs/content-types.md` (for guide structures)
  - `docs/ai-docs/style-guide.md` (for alert styles and formatting rules)

## Step-by-Step Workflow

1. **Discover Code Changes**: Review git diffs, commit logs, or the pull request details to understand what files and lines of code actually changed.
2. **Classify Changes**: Categorize the changes into the following groups:
   - **Added**: For new features or endpoints.
   - **Changed**: For modifications to existing behavior.
   - **Deprecated**: For features scheduled for removal.
   - **Removed**: For removed features.
   - **Fixed**: For bug fixes.
   - **Security**: In case of vulnerability fixes.
3. **Identify Breaking Changes**: Look for database migrations, env config updates, parameter removal, or signature changes that will cause failure for existing deployments.
4. **Draft the Changelog / Release Notes**:
   - Write short, clear bullet points for each category.
   - For breaking changes, write a prominent **Upgrade Guide** section using `> [!WARNING]` or `> [!IMPORTANT]` callouts.
   - Link to relevant task details or pull requests where possible.
5. **Verify and Link**: Ensure version numbers and dates are accurate.

## Validation Checklist
- [ ] Breaking changes are explicitly highlighted and explain how to upgrade.
- [ ] Every change bullet point is linked to actual code alterations (no hallucinated features).
- [ ] The version number follows Semantic Versioning (`MAJOR.MINOR.PATCH`).
- [ ] No internal secrets or environment parameters are exposed.

## Forbidden Actions
- **No Unexplained Breaking Changes**: Never list a breaking change without providing explicit upgrade instructions or configurations.
- **No Hypothetical Changelogs**: Do not invent entries. Document only the code that has actually been committed/changed.

## Final Response Format
Always include:
- Modified or new release documentation files
- Target release version and date
- Summary of breaking changes identified (if any)
- Upgrade instructions verified
