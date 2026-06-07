# Generate AI Documentation Framework Prompt

Use this prompt inside any software repository with an AI tool to bootstrap its repository-specific AI Documentation Framework.

---

You are working inside an existing software project repository.

Your task is to generate a complete AI Documentation Framework for this repository.

This framework will help developers and technical writers use AI coding assistants to write, update, structure, and audit project documentation consistently and safely.

This is a documentation-only and framework-only task.

Do NOT change application behavior.
Do NOT refactor production code.
Do NOT fix bugs.
Do NOT rename production files.
Do NOT change dependencies.
Do NOT create database migrations.
Do NOT include secrets, credentials, tokens, private keys, or sensitive production data.

---

## Main Objective

Create a repo-based AI Documentation Framework that gives AI assistants enough context to safely and accurately document this project.

The framework must help AI tools understand:

- What the product does.
- Who the target audiences are (e.g., developers, end-users, administrators).
- Where the main documentation portals and files are located.
- The writing, formatting, layout, and visual (Mermaid) standards.
- How to structure and write Tutorials and How-Tos.
- How to structure and write API References.
- How to structure and write Conceptual or Architectural Explanations.
- Pre-commit documentation checklists (e.g., link validation, snippet checks, formatting lints).
- Jargon, acronyms, and project-specific glossary terms.
- Specialized workflows/skills for documentation tasks.

Avoid generic documentation. Base the generated files on the actual structure and files in this repository.

---

## Discovery Phase

Before creating the files, inspect the codebase and existing documentation carefully.

1. **Identify the Project Archetype / Domain**:
   Analyze the codebase structure, dependencies, and configuration to determine the primary domain(s):
   - **SaaS / Web App / API Service**: Standard HTTP APIs (REST, GraphQL, RPC), user dashboards, and authentication. Look for routers, controllers, and web frameworks.
   - **CLI Tool / System Utility**: Shell commands, options, flags, and environment configs. Look for CLI parsing libraries (e.g., `clap`, `cobra`, `argparse`, `commander`).
   - **Software Library / SDK / Package**: Exported classes, namespaces, public functions, parameters, and exceptions. Look for package manifests (`package.json`, `setup.py`, `Cargo.toml`).
   - **Data Pipeline / ML / AI Model**: ETL processes, database schemas, model parameters, model cards, training/evaluation metrics, and data dictionaries. Look for data processing and model configurations.
   - **Embedded / IoT / Firmware**: Hardware registers, Pinouts, peripheral communication protocols (I2C, SPI), memory limits, and flashing procedures. Look for main loops, HALs, and C/C++ driver code.
2. **Review Existing Portals & Audiences**:
   - Location of existing documentation files (e.g., `README.md`, `docs/`, `wiki/`).
   - Identify target audiences (developers, end-users, administrators).
3. **Analyze Coding Conventions & Schemas**:
   - Extract parameters, API formats, and config options directly from the source code.

Do not assume anything without evidence.

If something is clearly found in the codebase or docs, document it normally.
If something is inferred, write: `Inferred from codebase: ...`
If something is important but unclear, write: `TBD - needs team confirmation`
If something is not found, write: `Not found in current codebase scan`

---

## Required Structure

Create this exact directory structure:

```txt
AGENTS.md
CLAUDE.md
GEMINI.md

docs/
└── ai-docs/
    ├── context.md
    ├── style-guide.md
    ├── content-types.md
    ├── review-policy.md
    └── glossary.md

.agents/
└── doc-skills/
    ├── api-documentation/
    │   └── SKILL.md
    ├── tutorial-writing/
    │   └── SKILL.md
    ├── architecture-explanation/
    │   └── SKILL.md
    ├── doc-audit/
    │   └── SKILL.md
    └── release-walkthrough/
        └── SKILL.md
```

---

## Token-Efficiency Requirement

The framework must avoid wasting tokens.

Use this principle:

> Small always-on context. Task-based documentation. Skill-based workflows. No full repository scan unless explicitly needed.

Rules:
- `docs/ai-docs/context.md` is the only default required read.
- Do not instruct AI tools to read all documentation files before every task.
- Do not instruct AI tools to load all skills before every task.
- Extra files should be read only when relevant.
- Only the relevant skill should be used.
- Normal tasks should inspect only impacted documentation folders and nearby source code.

---

## File Requirements

### 1. AGENTS.md
Create a short, strict, operational `AGENTS.md` containing:
- Default reading link to `docs/ai-docs/context.md`.
- Conditional reading links to style guides, templates, review checklists, and the glossary based on the task type.
- Mapping of skills to `.agents/doc-skills/`.
- Strict work rules (e.g., no hallucinating features, protect secrets, maintain link integrity, check code snippet signatures).
- Final response summary requirements (created files, changes made, checks performed, assumptions/TBDs).

### 2. CLAUDE.md
Create `CLAUDE.md` tailored for Claude Code agents. It should:
- Import only `@docs/ai-docs/context.md` by default.
- Specify conditional `@docs/ai-docs/` imports and `@.agents/doc-skills/` skills only when relevant to the task.
- Repeat core operational constraints matching `AGENTS.md`.

### 3. GEMINI.md
Create `GEMINI.md` tailored for Gemini-based models/agents. It should:
- Guide the model to load only `docs/ai-docs/context.md` by default.
- Specify conditional file reads and task skills.
- Outline token-efficient reading behavior and context management.
- Repeat core operational constraints matching `AGENTS.md`.

### 4. docs/ai-docs/context.md
Define the entry point context:
- Product name and summary.
- Main documentation portals and target audiences.
- **Project Archetype**: Explicitly document the identified archetype (SaaS/Web, CLI, Library/SDK, Data/ML, Embedded) based on your discovery.
- Core documentation sections.
- Critical rules and common risk areas.
- Token-efficient reading policy map.

### 5. docs/ai-docs/style-guide.md
Define writing and formatting rules:
- Tone, voice, and grammar guidelines.
- Markdown hierarchy rules (headings, bold UI elements, code formatting).
- GFM Alert callouts (`[!NOTE]`, `[!WARNING]`, etc.).
- Mermaid.js diagram guidelines (fenced block syntax, node label quoting, no raw HTML).
- Code snippets (syntax highlighting, ellipses, environment placeholders).

### 6. docs/ai-docs/content-types.md
Provide tailored templates and structures matching the identified project archetype:
- **Quickstarts**: Prerequisites, installation/setup, configuration, verification, next steps.
- **Tutorials / How-Tos**: Scenario description, step-by-step instructions, complete code/execution snippets, verification/testing.
- **Reference Documentation**: Provide a detailed layout matching the domain:
  - *Web App*: HTTP method, paths, auth scope, path/query parameter tables, payload schemas, success/error JSON response schemas, and cURL examples.
  - *CLI*: Command syntax, positional arguments, option tables, environment variables, exit codes, and console execution snippets.
  - *Library/SDK*: Class/interface declarations, property tables, method signatures, parameters, return types, exceptions, and code import examples.
  - *Data/ML*: Schema maps, ETL pipeline steps, model version tables, performance metrics, data sources, and model cards.
  - *Embedded*: Hardware pinouts, communication settings, register addresses, memory constraints, and compiling/flashing parameters.
- **Conceptual Explanations**: System design, data flow diagrams, design trade-offs.

### 7. docs/ai-docs/review-policy.md
Outline verification checklists:
- Link and path integrity (relative path validation, anchor matching).
- Formatting lints.
- Code snippet verification (parameters, signature check).
- Response format when performing reviews (Summary, Violations, Broken Links, Snippet Issues, Suggestions, TBDs).

### 8. docs/ai-docs/glossary.md
Create concise definitions for project-specific terms found in the repository or docs.

### 9. Documentation Skills (.agents/doc-skills/)
Create five `SKILL.md` files:
- **api-documentation/SKILL.md**: Guide for writing and updating public interface specs (HTTP APIs, CLI commands, class signatures, schemas, or register maps).
- **tutorial-writing/SKILL.md**: Guide for writing step-by-step onboarding walkthroughs, quickstarts, and how-tos.
- **architecture-explanation/SKILL.md**: Guide for system design overviews and Mermaid flowcharts.
- **doc-audit/SKILL.md**: Guide for link checking, syntax linting, and verifying code block signatures.
- **release-walkthrough/SKILL.md**: Guide for changelogs, upgrade notes, and release reviews based on git diffs.

Each skill file must start with YAML frontmatter:
```yaml
---
name: skill-name
description: Use this skill only for ...
---
```
Each skill must cover: Purpose, When to use, Required docs to read, Step-by-step workflow, Validation checklist, Forbidden actions, and Final response format.

---

## Final Output Required

After creating the files, respond with:

## Files Created
List all created documentation framework files.

## Codebase Areas Inspected
Summarize what parts of the repo you inspected.

## Key Findings
Summarize findings about target audiences, existing documentation quality, and primary system modules.

## Assumptions / Inferred Items
List anything inferred from the repository structure.

## TBD Items
List all items marked as `TBD - needs team confirmation`.

## Risks / Gaps
List missing or outdated documentation areas, broken links, or configuration ambiguities.

## Recommended Review Process
Suggest how the Tech Lead and team should review and approve these documentation files.
