---
name: docstruct
description: Use when creating, updating, auditing, or organizing software project documentation. Helps agents keep docs clear, non-duplicated, source-of-truth driven, and token-efficient.
license: MIT
metadata:
  author: Aetox Skills
  version: "0.1.1"
---

# DocStruct

## Purpose

Use DocStruct to create, update, audit, and organize project documentation without duplicate Markdown files, unclear ownership, unnecessary length, or token waste.

## When To Use

Use this skill when the task involves:

- initializing project documentation
- auditing existing docs
- deciding where documentation belongs
- reducing duplicated docs
- documenting APIs, features, architecture, or handoff state
- preparing docs so humans and agents can continue work safely

## When Not To Use

Do not use DocStruct when:

- a short README update is enough
- the user asks for marketing copy, a website, or a full docs platform
- legal, compliance, or regulated docs require a formal external standard
- the project already has a clear maintained documentation system

## Core Rules

- Read existing docs and nearby source files before writing.
- Update existing docs before creating new files.
- Create a file only when it has a clear responsibility.
- Keep one source of truth for each durable fact.
- Link instead of copying repeated details.
- Keep docs short by default; expand only when complexity requires it.
- Mark uncertain information as `UNKNOWN`.
- Mark required work as `TODO`.
- Do not invent missing implementation details.
- Remove or shorten documentation that does not help future work.

## Decision Flow

Before writing:

1. Find existing docs and README files.
2. Decide whether the information is useful for future work.
3. If a responsible file exists, update it.
4. If content is duplicated, keep the best source and replace copies with links.
5. If no responsible file exists, create the smallest useful document.
6. If information is uncertain, write `UNKNOWN` and state what to verify.

For more detail, read `references/decision-flow.md`.

## Single Source of Truth

Put each type of information in its responsible place:

- API behavior belongs in API docs.
- Database behavior belongs in database docs.
- UI behavior belongs in frontend docs.
- Deployment behavior belongs in deployment docs.
- Cross-system behavior belongs in architecture or integration docs.

Other files may link to the responsible source. Do not copy the same details into multiple files.

## Output Style

Write direct, compact Markdown. Prefer short sections, bullet lists, explicit status, and links to related files. Avoid decorative prose, long theory, placeholder files, and repeated background context.

## Status Labels

Use status labels to make continuation safe:

- `Current State`: what exists now
- `Implementation`: implemented, partial, planned, or unknown
- `Dependency`: required related file, system, or decision
- `Done`: confirmed completed work
- `Not Done`: known remaining work
- `TODO`: action required
- `UNKNOWN`: must be verified

For label guidance, read `references/status-labels.md`.

## Minimal Template

```md
# Title

## Purpose

## Status

- Current State:
- Implementation:
- Dependency:

## Notes

- ...

## Done

- [ ] ...

## Not Done

- [ ] ...

## Related Files

- `...`

## Notes for Agent

- ...
```

## References

- `references/decision-flow.md`: detailed documentation placement flow
- `references/status-labels.md`: status labels and examples
- `references/docstruct-principles.md`: concise DocStruct principles
- `templates/`: reusable Markdown templates
- `prompts/`: ready-to-use initialization and audit prompts
- `adapters/`: Cursor and AGENTS.md examples

## Final Instruction

The best documentation is the smallest structure that preserves clarity, ownership, and continuity.
