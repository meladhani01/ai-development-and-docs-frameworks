# AI Assistant Framework Templates

[![GitHub Repository](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/meladhani01/ai-development-and-docs-frameworks)

A collection of repo-based, token-efficient AI operating framework templates to standardize how software engineering and technical writing teams use AI assistants (such as Antigravity, Claude Code, Codex, Cursor, or Gemini Gems) consistently and safely.

The core design philosophy is simple:
> **Stop relying on ephemeral chat histories. Embed project context, engineering guidelines, style systems, and specialized agent skills directly in the repository.**

---

## What This Repository Contains

This repository houses two distinct, copyable framework templates:

```txt
.
├── LICENSE
├── README.md                              # Global Repository Guide
│
├── development-framework/                 # Template for AI Code Modification
│   ├── AGENTS.md                          # Dev Agent Core Rules
│   ├── CLAUDE.md                          # Claude Code Dev Configuration
│   ├── docs/
│   │   └── ai/                            # Context, Architecture, Testing, Security Policies
│   └── .agents/
│       └── skills/                        # Workflows: backend/frontend changes, bug-fix, review, etc.
│
├── documentation-framework/               # Template for AI Technical Writing & Auditing
│   ├── AGENTS.md                          # Doc Agent Core Rules
│   ├── CLAUDE.md                          # Claude Code Doc Configuration
│   ├── GEMINI.md                          # Gemini Doc Configuration
│   ├── docs/
│   │   └── ai-docs/                       # Context, Style Guide, Content Types, Review Policies
│   └── .agents/
│       └── doc-skills/                    # Workflows: reference-writing, tutorials, audits, etc.
│
└── examples/                              # Automatic Bootstrapping Prompt Templates
    ├── generate-framework-prompt.md      # Auto-generates Dev Framework
    ├── generate-doc-framework-prompt.md  # Auto-generates Doc Framework
    ├── review-framework-prompt.md        # Reviews Target Dev Framework
    └── review-doc-framework-prompt.md    # Reviews Target Doc Framework
```

---

## 1. AI Development Framework

**Designed for**: Automating code creation, system refactoring, testing, and debugging.

It provides coding agents with standard structures for:
- Understanding the core system architecture and module dependencies.
- Writing code that conforms to languages, design patterns, and lint conventions.
- Accessing database security structures, APIs, and permission scopes.
- Performing unit, integration, and E2E testing.
- Evaluating release readiness and rollback procedures.

👉 Learn more in the [development-framework/](./development-framework/) directory.

---

## 2. AI Documentation Framework

**Designed for**: Writing, revising, restructuring, and auditing technical documentation.

It supports multiple **Project Archetypes** (SaaS/Web Services, CLI utilities, SDKs/Libraries, Data/ML pipelines, and Embedded/Hardware systems) and details:
- Tone, grammar, and typography rules.
- GFM Callouts and Mermaid.js flow diagram configurations.
- Layout guides for Quickstarts, Tutorials, API reference guides, and Conceptual architectures.
- Workflows for auditing broken paths, verifying code snippet signatures, and drafting changelogs.

👉 Learn more in the [documentation-framework/](./documentation-framework/) directory.

---

## Core Concept: Token-Efficiency

AI models compile files into context windows. Scanning entire repositories or reading huge guidelines on every single turn quickly wastes context windows and increases latency.

These templates employ a **lazy-loading, token-efficient model**:

```txt
Always Read First:
- AGENTS.md (Root rules)
- docs/[ai|ai-docs]/context.md (Default project snapshot)

Read Conditionally (Only when task matches):
- style-guide.md       → For page layout or syntax checks
- testing-policy.md    → When changing behavior and verifying code
- security-policy.md   → When auditing credentials or permissions
- glossary.md          → To clarify ambiguous domain jargon

Execute via Target Skills:
- Load only the single SKILL.md file matching the operational task (e.g. bug-fix or tutorial-writing).
```

---

## How to Adopt These Templates

### Option 1: Manual Integration
Choose which framework you want to integrate (or adopt both side-by-side):

1. **For Development Guidelines**: Copy the files/folders under `development-framework/` into the root of your project repository.
2. **For Documentation Guidelines**: Copy the files/folders under `documentation-framework/` into the root of your project repository.
3. Edit the template files (marked with `TBD - needs team confirmation` or placeholder details) to match your real project.

### Option 2: Automatic Bootstrapping
You can instruct an AI agent to read your codebase and generate/review a tailored framework automatically:

1. Open your target codebase in your AI editor or coding tool.
2. **To Bootstrap Development**: Copy the prompt in [generate-framework-prompt.md](./examples/generate-framework-prompt.md) and paste it. After generation, run the review prompt in [review-framework-prompt.md](./examples/review-framework-prompt.md).
3. **To Bootstrap Documentation**: Copy the prompt in [generate-doc-framework-prompt.md](./examples/generate-doc-framework-prompt.md) and paste it. After generation, run the review prompt in [review-doc-framework-prompt.md](./examples/review-doc-framework-prompt.md).
4. The AI will audit your repo and generate/validate customized context, guidelines, and skills.

---

## Customization Checklist

Before deploying the templates in production, make sure to update:
- **Product Details**: Product name, primary users, and business scope.
- **Paths & Folders**: Correct directories for sources, tests, configs, and assets.
- **Security Protocols**: Role and permission logic, tenant data constraints, and PII rules.
- **Commands**: Build targets, linters, testing commands, and flashing parameters.
- **Glossary**: Domain vocabulary and acronym definitions.

---

## License

This repository is licensed under the MIT License. Feel free to copy, modify, and distribute it across your projects.
