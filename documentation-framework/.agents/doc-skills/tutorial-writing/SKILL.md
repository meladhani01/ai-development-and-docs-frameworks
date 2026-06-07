---
name: tutorial-writing
description: Use this skill only for creating, updating, or reviewing step-by-step developer tutorials, quickstarts, and how-to guides.
---

# Skill: Tutorial & How-To Guide Creation

## Purpose
Help developers and users learn how to use the project or implement a specific task by creating clear, structured, progressive tutorials.

## When to Use
Use this skill when:
- Creating or revising a "Getting Started" or "Quickstart" guide.
- Writing how-to guides for common development procedures:
  - *Web App*: "How to configure OAuth login" or "How to handle session cookies".
  - *CLI Tool*: "How to structure nested options" or "How to pipe stdout".
  - *Library/SDK*: "How to configure SDK clients" or "How to register custom middleware".
  - *Data/ML*: "How to execute ETL jobs" or "How to run local inference".
  - *Embedded*: "How to set GPIO pins" or "How to flash bootloaders".
- Updating existing walkthroughs to match code updates.

## Required Documents to Read
- Default: `docs/ai-docs/context.md`
- Conditional:
  - `docs/ai-docs/content-types.md` (specifically Tutorial/How-To structures)
  - `docs/ai-docs/style-guide.md` (for typography, lists, and callout guidelines)

## Step-by-Step Workflow

1. **Establish Goal and Audience**: Define what the user will achieve and what their background knowledge should be.
2. **Review Prerequisites**: Identify exactly what software, SDK versions, credentials, hardware boards, or setups are needed before the user can begin the tutorial.
3. **Inspect Implementation Reference**: Check the codebase, dependencies, test scripts, or board specifications to ensure instructions are 100% accurate and use current conventions.
4. **Draft the Tutorial**:
   - Write a clear introduction of the end result.
   - Outline steps in sequence. Use bold text for UI controls, directories, and interface options.
   - Embed complete, concise code, terminal execution, or config snippets with comments explaining key lines.
5. **Add Verification and Testing Steps**: Explicitly write how the user can verify their progress at intermediate points and at the end of the guide.
6. **Add Troubleshooting tips**: Address typical friction points, compiler flags, or common error messages.

## Validation Checklist
- [ ] Prerequisites list the required tool versions correctly.
- [ ] Code examples match coding standards and use modern conventions.
- [ ] Every step includes a brief explanation of *why* it is performed.
- [ ] Clear instructions on how to test/verify that the tutorial worked.
- [ ] Markdown is clean, headings are sequential, and alert callouts are formatted correctly.

## Forbidden Actions
- **No Conceptual Bloat**: Keep theory minimal. Focus on practical execution.
- **No Incomplete Snippets**: Do not skip imports, exports, or configuration keys that would prevent the code from compiling or running.
- **No Hardcoded Secrets**: Do not use real passwords or access keys in examples.

## Final Response Format
Always include:
- New or modified tutorial files
- Brief summary of the tutorial goal
- Key prerequisites and verification steps documented
- Assumptions made
