# Documentation Review Policy

All documentation updates must be audited for correctness, consistency, formatting, and link integrity before integration.

---

## 1. Automated & Manual Checklist

AI agents and reviewers must run the following checks on any modified or new documentation files:

### Link and Path Integrity
- [ ] **Relative Links**: Ensure all relative file paths (e.g., `[details](../auth/setup.md)`) point to valid, existing files in the repository.
- [ ] **Section Anchors**: Verify that links pointing to specific headers (e.g., `[Setup](#setup-steps)`) match the target header exactly (all lowercase, spaces replaced with hyphens, special characters removed).
- [ ] **External Links**: Confirm there are no typos in external URLs (e.g., `https://` protocols).

### Formatting and Linting
- [ ] **Heading Order**: Check that heading levels nest sequentially without skipping levels.
- [ ] **Fenced Code Blocks**: Ensure all code blocks are closed and have their language specified (e.g., ` ```bash `).
- [ ] **Clean Tables**: Verify table columns align correctly and markdown syntax is complete.
- [ ] **No Raw HTML**: Verify that formatting uses markdown syntax rather than inline HTML (except where explicitly allowed like carousels).

### Code Snippet Verification
- [ ] **Signature Check**: Compare function signatures and API parameters in documentation snippets against the actual implementation in the codebase.
- [ ] **Command Syntax**: Double check that CLI commands are valid and all parameters match current tool versions.
- [ ] **No Credentials**: Confirm that no passwords, private keys, or API tokens are checked into code blocks.

### Completion Verification
- [ ] **No Placeholders**: Check that there are no remaining `TODO`, `TBD`, or template brackets (e.g., `<insert here>`) in the final draft, unless explicitly marked as `TBD - needs team confirmation`.

---

## 2. Review Output Format

When an AI agent is tasked with reviewing documentation, it must use this exact structure for its response:

```markdown
## Documentation Review Summary
[Provide a brief overview of the changes made and if they meet style/content guidelines.]

## Formatting & Style Violations
- [List any heading level jumps, spacing issues, or casing violations.]
- [If none, state "None detected."]

## Broken Links & Paths
- [List any relative or external links that fail validation.]
- [If none, state "None detected."]

## Code Snippet Issues
- [Identify mismatched signatures, outdated CLI options, or exposed credentials.]
- [If none, state "None detected."]

## Suggested Improvements
- [Suggest wording improvements, adding helpful diagrams, or adding more context.]

## Questions & TBDs
- [List any assumptions or items that require team/tech lead clarification.]
```
