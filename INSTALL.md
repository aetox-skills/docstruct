# Install DocStruct

DocStruct is an agent skill package. The primary installable file is
`SKILL.md`.

## Source Of Truth

- `SKILL.md`: core skill instructions for all agents.
- `agents/openai.yaml`: Codex/OpenAI interface metadata only.
- `adapters/agents-md/AGENTS.example.md`: optional project instruction adapter.
- `adapters/cursor/docstruct.mdc`: optional Cursor rule adapter.

## Codex

Install from GitHub:

```txt
aetox-skills/docstruct
```

Common local skill paths:

```txt
Windows: %USERPROFILE%\.codex\skills\docstruct
macOS:   ~/.codex/skills/docstruct
Linux:   ~/.codex/skills/docstruct
```

Restart Codex after installation so the skill list refreshes.

## Claude Code

Use `SKILL.md` as the project instruction source.

One practical pattern is to add a project `CLAUDE.md` that imports the skill:

```md
# Project Instructions

Use DocStruct when creating, updating, auditing, or organizing project
documentation.

@/absolute/path/to/docstruct/SKILL.md
```

Use a real absolute path for the machine where Claude Code runs.

## Antigravity Or Other Agent Runtimes

Use the root `SKILL.md` as the skill instruction file when your runtime supports
skills.

If the runtime supports `AGENTS.md`-style project instructions, copy or merge:

```txt
adapters/agents-md/AGENTS.example.md
```

into the target project's `AGENTS.md`.

## Manual Use

Clone the repository and ask the agent to read `SKILL.md` before documentation
work:

```sh
git clone https://github.com/aetox-skills/docstruct.git
```

Use this prompt:

```txt
Use DocStruct to inspect the project documentation, avoid duplication, keep one
source of truth, and mark TODO or UNKNOWN items clearly.
```

## Cursor Rules

Copy `adapters/cursor/docstruct.mdc` into your Cursor rules folder, or adapt
its content into an existing project rule.

Use it when Cursor should keep project documentation concise, non-duplicated,
and source-of-truth driven.

## AGENTS.md Usage

Copy `adapters/agents-md/AGENTS.example.md` into a project's `AGENTS.md`, or
merge its DocStruct section into an existing `AGENTS.md`.

This is useful when multiple coding agents need the same documentation behavior
in one repository.
