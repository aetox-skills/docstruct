# Install DocStruct

DocStruct is an agent skill package. The primary installable file is `SKILL.md`.

## Generic AI Agents

Copy `SKILL.md` into the agent's system prompt, skill registry, or reusable instruction area. Keep the `references/`, `templates/`, and `prompts/` folders available when the agent can read local files.

Use this prompt:

```txt
Use DocStruct to inspect the project documentation, avoid duplication, keep one source of truth, and mark TODO or UNKNOWN items clearly.
```

## Codex-Style Skills

Install the repository as a skill folder so the root `SKILL.md` is discoverable:

```txt
docstruct/
  SKILL.md
  references/
  templates/
  prompts/
```

Then ask Codex to use the `docstruct` skill when creating, updating, or auditing documentation.

## Claude-Style Skills

Use `SKILL.md` as the skill instruction file. Keep the repository folders beside it so Claude can load references and templates as needed.

Recommended instruction:

```txt
Use the DocStruct skill. Read SKILL.md first. Load references only when needed.
```

## Cursor Rules

Copy `adapters/cursor/docstruct.mdc` into your Cursor rules folder, or adapt its content into an existing project rule.

Use it when Cursor should keep project documentation concise, non-duplicated, and source-of-truth driven.

## AGENTS.md Usage

Copy `adapters/agents-md/AGENTS.example.md` into a project's `AGENTS.md`, or merge its DocStruct section into an existing `AGENTS.md`.

This is useful when multiple coding agents need the same documentation behavior in one repository.
