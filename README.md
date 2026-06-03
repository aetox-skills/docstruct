# DocStruct

DocStruct is an open-source documentation architecture skill that teaches AI agents how to create clear, non-duplicated, token-efficient project documentation.

![DocStruct documentation architecture](เอกสารที่ถูกจัดระเบียบ.png)

## Why This Exists

AI agents often create too many Markdown files, repeat facts, and leave unclear ownership. DocStruct gives agents a small set of rules for deciding where documentation belongs, when to update existing files, and when a new file is useful.

## Core Idea

Write less documentation, but better documentation.

A useful documentation structure separates information by responsibility, keeps one source of truth, marks unknowns clearly, and preserves enough context for humans and agents to continue safely.

## Principles

- Read before writing.
- Use the smallest useful document.
- Link instead of copying.
- Keep ownership clear.
- Put API details in API docs.
- Put database details in database docs.
- Keep frontend and backend behavior separate unless a file is explicitly about integration.
- Mark `TODO` and `UNKNOWN` instead of inventing details.
- Avoid decorative documentation.
- Remove or shorten docs that no longer help.

## Who It Is For

DocStruct is for:

- AI coding agents
- open-source maintainers
- small software teams
- projects that want useful docs without a heavy framework
- humans reviewing or continuing AI-generated work

## When To Use

Use DocStruct when:

- initializing documentation for a project
- auditing an existing `docs/` folder
- deciding where new documentation should live
- reducing duplicated Markdown content
- preparing project context for AI agents
- keeping documentation compact for repeated agent workflows

## When Not To Use

Do not use DocStruct when:

- you need a full documentation website
- you need product marketing pages
- legal, compliance, or regulated documentation requires a formal structure
- the project already has a well-maintained documentation architecture
- a short README is enough

## Quick Start

1. Copy one skill file into your agent instructions:
   - `skill/docstruct.skill.md` for the standard version
   - `skill/compact.skill.md` for low-token usage
2. Ask the agent to inspect the project before writing.
3. Use one of the prompts in `prompts/`.
4. Keep only documents with a clear responsibility.

## Recommended Usage Prompts

Initialize documentation:

```txt
Use DocStruct to inspect this project and create a minimal docs structure. Update existing documentation first. Create only useful files. Mark TODO and UNKNOWN items clearly.
```

Audit documentation:

```txt
Use DocStruct to audit the existing documentation for duplication, unclear ownership, stale information, over-documentation, and missing next steps.
```

Compact mode:

```txt
Use compact DocStruct rules. Keep the documentation structure minimal and token-efficient.
```

## Project Structure

```txt
.
|-- README.md
|-- LICENSE
|-- CHANGELOG.md
|-- skill/
|   |-- README.md
|   |-- docstruct.skill.md
|   `-- compact.skill.md
|-- prompts/
|   |-- README.md
|   |-- initialize-docs.prompt.md
|   `-- audit-docs.prompt.md
|-- templates/
|   |-- README.md
|   |-- minimal-doc.template.md
|   `-- api-doc.template.md
`-- examples/
    |-- README.md
    `-- small-project/
        `-- docs/
            |-- README.md
            |-- api/
            |   `-- auth-api.md
            `-- frontend/
                `-- login-page.md
```

## License

MIT. See `LICENSE`.
