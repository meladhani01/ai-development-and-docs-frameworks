# Documentation Context

Replace this file with project-specific documentation context generated from your real codebase and wiki.

This is the only shared context file that AI documentation tools should read by default.

## Documentation Summary

- Product Name: `TBD - needs team confirmation`
- Main Portals: (e.g., `docs/` folder, GitBook, Readme.io, Docusaurus, wiki) `TBD - needs team confirmation`
- Primary Audiences:
  - Developers: (e.g., API references, system design) `TBD - needs team confirmation`
  - End Users: (e.g., how-tos, UI walkthroughs) `TBD - needs team confirmation`
  - Administrators: (e.g., deployment guides, configurations) `TBD - needs team confirmation`

## Project Archetype

Identify the project's primary domain type:
- **SaaS / Web App / API Service**: Standard HTTP APIs (REST, GraphQL, RPC), user dashboards, and authentication.
- **CLI Tool / System Utility**: Shell command options, arguments, exit statuses, configurations, and environment variables.
- **Software Library / SDK / Package**: Classes, namespaces, public functions, parameters, return types, exceptions, and installation via package managers.
- **Data Pipeline / ML / AI Model**: ETL processes, database schemas, model parameters, model cards, training/evaluation metrics, and data dictionaries.
- **Embedded / IoT / Firmware**: Hardware registers, Pinouts, device communication protocols (I2C, SPI), memory limits, and flashing procedures.

Current Archetype: `TBD - needs team confirmation`

## Core Doc Sections

Document only documentation sections that exist in the repository:

- API Reference
- Quickstart Guide
- Deployment & Operations
- Tutorials & Cookbooks
- Architecture & System Design
- Release Notes & Changelog

## Critical Rules

- **No Hallucinated Features**: Only document features that exist in the codebase.
- **Strict Anonymization**: Never use real server hostnames, credentials, or client keys.
- **Link Check**: Every link added must be checked for validity.
- **No Large Rewrites**: When correcting typos or adding a note, edit only the target paragraph. Avoid rewriting the entire page unless requested.

## Common Risk Areas

- **Deprecated Features**: Documenting features that are marked for removal or replaced.
- **Outdated Snippets**: Code or command line examples that fail with current dependencies.
- **Broken Internal Links**: Relative paths in markdown that break when files are moved.
- **Configuration Scoping**: Recommending insecure default configurations.

## AI Documentation Working Policy

Before editing or creating documentation:

1. Read this file.
2. Understand the request and target audience.
3. Inspect only the relevant documentation files and corresponding source code.
4. Make the smallest safe edit.
5. Verify relative links and markdown formatting.
6. Provide a concise changelog in the final response.

## Token-Efficient Reading Policy

Always read this file first.

Then read other docs only when relevant:

- Layouts, styling, typography, colors, Mermaid → `docs/ai-docs/style-guide.md`
- Templates (Tutorials, APIs, Concept Guides) → `docs/ai-docs/content-types.md`
- Link validation, review checks, code snippet testing → `docs/ai-docs/review-policy.md`
- Unclear jargon or product terminology → `docs/ai-docs/glossary.md`
