# DocStruct

DocStruct is an installable documentation architecture skill for AI agents. It teaches agents how to create clear, non-duplicated, source-of-truth driven, token-efficient project documentation.

![DocStruct documentation architecture](assets/docstruct-preview.png)

## What Makes DocStruct Different?

DocStruct is not a Markdown template repo. It is an agent behavior package.

It tells agents how to decide:

- when to update existing docs instead of creating new files
- where each type of documentation belongs
- how to avoid duplicated Markdown content
- how to mark `TODO` and `UNKNOWN` information clearly
- how to keep documentation small enough for repeated agent workflows

## Install / Use

Use [SKILL.md](SKILL.md) as the primary installable skill file.

For setup options, see [INSTALL.md](INSTALL.md).

Quick use:

```txt
Use DocStruct to inspect this project, update existing docs before creating new files, keep one source of truth, and mark TODO or UNKNOWN items clearly.
```

## Compatibility

DocStruct includes adapters for:

- generic AI agents using [SKILL.md](SKILL.md)
- Codex-style skills
- Claude-style skills
- Cursor rules via [adapters/cursor/docstruct.mdc](adapters/cursor/docstruct.mdc)
- `AGENTS.md` workflows via [adapters/agents-md/AGENTS.example.md](adapters/agents-md/AGENTS.example.md)

## Core Rules

- Read before writing.
- Use the smallest useful document.
- Update existing docs before creating new files.
- Keep one source of truth.
- Link instead of copying.
- Mark `TODO` and `UNKNOWN` instead of inventing details.
- Avoid decorative or placeholder documentation.

## Repository Structure

```txt
.
|-- SKILL.md
|-- INSTALL.md
|-- README.md
|-- CHANGELOG.md
|-- references/
|-- adapters/
|-- prompts/
|-- templates/
|-- skill/
|-- examples/
`-- assets/
```

## License

MIT. See [LICENSE](LICENSE).
