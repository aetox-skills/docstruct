# DocStruct Skill

## Purpose

Help an AI agent create, update, audit, and organize project documentation with
clear ownership, minimal duplication, and low token cost.

Use this when working on `docs/` folders, README files, feature docs, API docs,
architecture notes, or agent handoff notes.

## Core Behavior

When asked to work on documentation:

1. Inspect the existing project and documentation before writing.
2. Identify the smallest structure that explains the project clearly.
3. Update existing documents before creating new files.
4. Create a new file only when it has a distinct responsibility.
5. Keep content concise unless complexity requires more detail.
6. Link to the source document instead of copying the same information.
7. Mark uncertain or missing information as `TODO` or `UNKNOWN`.
8. Avoid decorative, generic, or speculative documentation.

## Decision Flow

Before writing, decide:

1. Does a relevant document already exist?
   - Yes: update it.
   - No: continue.
2. Is the information important for future work?
   - Yes: continue.
   - No: do not document it.
3. Does this information belong in an existing file by responsibility?
   - Yes: add it there.
   - No: continue.
4. Does the topic need its own file because it has a separate owner, workflow, API group, or subsystem?
   - Yes: create the smallest useful file.
   - No: add a short note to the nearest responsible file.

## Token Discipline

Documentation should reduce future token cost. Prefer:

- short sections
- direct language
- bullet lists for state and next steps
- links to related files
- summaries of decisions

Avoid:

- long explanations of obvious behavior
- repeated background context
- broad theory
- verbose status updates
- copying code into docs unless needed to explain an interface

Expand only when the project complexity requires it.

## Read Before Write Rule

Always inspect existing files before creating documentation. Read:

- the repository root README
- existing `docs/` files
- nearby source files for the feature being documented
- configuration files when they affect behavior

Do not assume the current request contains the full truth. Do not invent missing implementation details.

## Single Source of Truth

Each durable fact should live in one responsible place:

- API endpoint behavior belongs in an API doc.
- Database schema behavior belongs in a database doc.
- UI behavior belongs in a frontend doc.
- Deployment behavior belongs in a deployment doc.
- Cross-system behavior belongs in an integration or architecture doc.

Other documents may link to that source. Do not duplicate it.

## File Responsibility Rule

Every documentation file should have one clear responsibility. A file is useful when it explains:

- one feature
- one API group
- one subsystem
- one workflow
- one architecture decision
- one project-level overview

If a file mixes unrelated responsibilities, split it. If several files repeat the same responsibility, merge them.

## Status Labels

Use status labels so agents can continue work safely.

Recommended labels:

- `Current State`: what exists now
- `Implementation`: implemented, partial, planned, or unknown
- `Dependency`: required related system, feature, or file
- `Done`: confirmed completed work
- `Not Done`: known remaining work
- `TODO`: action needed
- `UNKNOWN`: information that must be verified

Do not hide uncertainty in vague language.

## Unknown Information Rule

If information is missing, uncertain, or not verified:

- write `UNKNOWN`
- write `TODO`
- name what must be checked
- avoid guessing

Example:

```md
- Auth provider: UNKNOWN. TODO: verify in backend auth configuration.
```

## Minimal Template

Use this for most small documents:

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

## Full Template

Use this only when the minimal template is not enough:

```md
# Title

## Purpose

## Status

- Current State:
- Implementation:
- Dependency:

## Key Behavior

## Interfaces

## Done

## Not Done

## Related Files

## Notes for Agent
```

## Anti-Patterns

Avoid:

- creating files just to fill a folder
- duplicating endpoint details across frontend and API docs
- writing database details outside database docs
- mixing frontend and backend logic in one feature doc without clear reason
- creating huge project overviews that no one will maintain
- writing generic Markdown templates as if they are finished docs
- inventing implementation details
- adding long prose when a status list is enough
- creating a documentation framework before the project needs one

## Final Instruction

The best documentation is the smallest structure that preserves clarity, ownership, and continuity.
