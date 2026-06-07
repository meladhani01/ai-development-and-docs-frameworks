---
name: architecture-explanation
description: Use this skill only for explaining, documenting, or updating descriptions of the system design, code architecture, modules, data flows, and structural decisions.
---

# Skill: Architecture & System Design Explanation

## Purpose
Produce high-quality architectural descriptions and data-flow diagrams to help developers understand the structural design and engineering principles of the codebase.

## When to Use
Use this skill when:
- Creating or editing system design documents (e.g., `architecture.md`).
- Explaining data pipelines, component relations, request lifecycles, or message queues.
- Documenting engineering design decisions and structural conventions.

## Required Documents to Read
- Default: `docs/ai-docs/context.md`
- Conditional:
  - `docs/ai-docs/content-types.md` (Conceptual & Architecture Explanation layouts)
  - `docs/ai-docs/style-guide.md` (specifically Mermaid diagram syntax)

## Step-by-Step Workflow

1. **Perform Directory Discovery**: Walk the directory tree to verify paths, naming conventions, and layer structures (e.g., model-view-controller, clean architecture, microservices).
2. **Trace Key Transactions**: Follow a core operation (e.g., standard login flow or API request-response loop) through the modules to map the sequence of operations.
3. **Establish Mermaid Diagram Layout**:
   - Sketch out the diagram flow: graph direction (TD or LR), components, and arrows.
   - Standardize styling and ensure node labels containing special characters are safely quoted (e.g., `A["Controller (HTTP REST)"]`).
4. **Draft the Document**:
   - Write a high-level overview.
   - Describe each layer and its specific responsibility.
   - Reference exact directory paths (with links) rather than general folder names.
   - Explain the "why" behind the design patterns used.
5. **Verify Accuracy**: Cross-reference the description against the real controller, model, or service locations.

## Validation Checklist
- [ ] Diagram syntax is valid Mermaid code (no unquoted special characters).
- [ ] Directory paths are written correctly and link to actual source folders.
- [ ] Explains separation of concerns between components.
- [ ] No unconfirmed architectural plans (unless clearly marked as `TBD - needs team confirmation`).

## Forbidden Actions
- **No Theoretical Overreach**: Do not write essays on general design patterns. Tie every concept directly to the actual files and code patterns in the repository.
- **No Outdated Flow Diagrams**: Ensure diagrams accurately reflect current import trees and routing mechanisms.

## Final Response Format
Always include:
- Modified or new architecture files
- System design areas documented (e.g., storage layer, auth lifecycle)
- Main modules and directories linked
- Diagrams updated
