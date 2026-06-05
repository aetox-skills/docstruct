# DocStruct

DocStruct is an AI documentation architecture skill for creating, updating,
auditing, and organizing clear, non-duplicated, source-of-truth driven,
token-efficient project documentation.

It teaches AI agents where documentation belongs, when to update existing
Markdown, and when a new file is actually useful.

![DocStruct documentation architecture](assets/docstruct-preview.png)

## What Makes DocStruct Different?

DocStruct is not a Markdown template repo. It is an agent behavior package.

It tells agents how to decide:

- when to update existing docs instead of creating new files
- where each type of documentation belongs
- how to avoid duplicated Markdown content
- how to mark `TODO` and `UNKNOWN` information clearly
- how to keep documentation small enough for repeated agent workflows

## Use When

- An AI agent needs to initialize or audit project documentation.
- A project has duplicated or unclear Markdown files.
- Documentation needs clear ownership and one source of truth.
- A team wants compact docs that future humans and AI agents can continue from.
- The task is documentation structure, not architecture mapping or product
  planning.

## Do Not Use When

- A short README edit is enough.
- The user needs product marketing copy or a documentation website.
- Legal, compliance, or regulated documentation requires a formal external
  standard.
- The task is architecture mapping, system boundary review, or raw-idea
  architecture proposal work.

## Relationship To Other Aetox Skills

DocStruct focuses on documentation structure and documentation ownership.

Use [`senior-architect-agent`](https://github.com/aetox-skills/senior-architect-agent)
for existing system mapping, architecture documentation, Mermaid architecture
diagrams, and AI agent handoff.

Use [`idea-to-architecture-agent`](https://github.com/aetox-skills/idea-to-architecture-agent)
for turning raw ideas, product concepts, feature requests, or business goals
into reviewable architecture proposals.

## Quick Use

Choose the path that matches your agent:

1. **Generic AI Agent**
   Copy [SKILL.md](SKILL.md) into your agent instruction context.

2. **Cursor**
   Copy [adapters/cursor/docstruct.mdc](adapters/cursor/docstruct.mdc) into `.cursor/rules/docstruct.mdc`.

3. **AGENTS.md**
   Copy [adapters/agents-md/AGENTS.example.md](adapters/agents-md/AGENTS.example.md) into your project as `AGENTS.md`.

## Use DocStruct With Your Agent

Use this prompt after adding the matching instruction file:

```txt
Use DocStruct to inspect this project, update existing docs before creating new
files, keep one source of truth, and mark TODO or UNKNOWN items clearly.
```

For more setup options, see [INSTALL.md](INSTALL.md).

## Compatibility

DocStruct includes adapters for:

- generic AI agents using [SKILL.md](SKILL.md)
- Codex-style skills
- Claude-style skills
- Cursor rules via
  [adapters/cursor/docstruct.mdc](adapters/cursor/docstruct.mdc)
- `AGENTS.md` workflows via
  [adapters/agents-md/AGENTS.example.md](adapters/agents-md/AGENTS.example.md)

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
|-- agents/
|-- references/
|-- adapters/
|-- prompts/
|-- templates/
|-- skill/
|-- examples/
`-- assets/
```

## Example Outputs

- Small project documentation example:
  [`examples/small-project/docs/`](examples/small-project/docs/)

## Install

Install this Codex skill from:

```txt
aetox-skills/docstruct
```

## License

MIT. See [LICENSE](LICENSE).
