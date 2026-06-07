---
name: api-documentation
description: Use this skill only for documenting API endpoints, routing, schemas, request/response models, and error responses.
---

# Skill: Reference & API Documentation

## Purpose
Produce accurate, structured, and developer-friendly documentation for the project's public interfaces (Web APIs, CLI subcommands, SDK classes/functions, Data/ML schemas, or Embedded registries) based on actual codebase definitions.

## When to Use
Use this skill when:
- Designing or updating HTTP API endpoints (REST/GraphQL/gRPC).
- Documenting CLI command arguments, options, flags, and exit codes.
- Specifying public classes, interfaces, methods, exceptions, and properties in an SDK or library.
- Mapping database tables, ETL schemas, feature stores, or Machine Learning model cards.
- Specifying hardware pinouts, communication registers, or microcontroller configurations.

## Required Documents to Read
- Default: `docs/ai-docs/context.md`
- Conditional: `docs/ai-docs/content-types.md` (Section 3: Reference Documentation templates)

## Step-by-Step Workflow

1. **Identify Project Archetype**: Read [context.md](file:///d:/Copto/ai-assisted-development-framework/documentation-framework/docs/ai-docs/context.md) to check the target project archetype (SaaS/Web, CLI, Library/SDK, Data/ML, Embedded).
2. **Locate Source Definitions**: Find the source code defining the interface:
   - *Web App*: Controller classes, router definitions, validation schemas.
   - *CLI Tool*: CLI parser configuration (e.g., `argparse`, `commander`, `clap`).
   - *Library / SDK*: Source file declarations of classes, types, structs, or methods.
   - *Data / ML*: Database migration scripts, ORM schemas, pipeline definitions, model training configs.
   - *Embedded*: Driver files, peripheral headers, registry definitions, memory maps.
3. **Extract Parameters and Types**: Identify path/query inputs, command-line arguments/options, method parameter types/returns/exceptions, table columns, or registry bits.
4. **Draft the Specification**: Write or edit the target Markdown reference file using the corresponding template layout from [content-types.md](file:///d:/Copto/ai-assisted-development-framework/documentation-framework/docs/ai-docs/content-types.md#3-reference-documentation).
5. **Construct Concrete Usage Examples**: Build copy-pasteable execution examples (e.g., cURL commands, CLI execution blocks, code import snippets, DataFrame schemas, registry configurations).
6. **Verify and Lint**: Run the review policy checklists to check formatting, code fences, and links.

## Validation Checklist
- [ ] Mapped all parameters, types, and constraints directly from the source code.
- [ ] Documented error states, exceptions, or failure conditions alongside success states.
- [ ] Ensure all code and configuration blocks are valid code.
- [ ] No hardcoded authentication tokens, API keys, or customer credentials.

## Forbidden Actions
- **No Hallucinated Parameters**: Do not invent subcommands, parameters, exceptions, or registry bits. If it is not in the codebase, it does not exist in the docs.
- **No Large-Scale Rewrites**: Limit changes only to files relevant to the public interface modification.

## Final Response Format
Always include:
- Changed files
- Brief summary of the interface changes documented
- Public endpoints, commands, classes, schemas, or registers updated
- Verification steps taken
