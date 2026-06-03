# Initialize Project Documentation Prompt

Use DocStruct to initialize documentation for this software project.

## Instructions

1. Inspect the existing project structure before writing.
2. Check whether a `docs/` folder already exists.
3. Read the root `README.md` and any existing documentation.
4. Create only useful folders.
5. Do not create empty placeholder files.
6. Create or improve `docs/README.md`.
7. Avoid duplicated content.
8. Prefer a compact structure unless the project is clearly complex.
9. Update existing documents before creating new files.
10. Mark uncertain information as `TODO` or `UNKNOWN`.

## Output Required

Return:

- proposed docs structure
- files to create
- purpose of each file
- existing files to update
- duplicated content to avoid or remove
- `TODO` items
- `UNKNOWN` items

## Constraints

- Keep documentation concise.
- Do not create a large documentation framework.
- Do not add folders without a clear responsibility.
- Do not invent implementation details.
- Link to existing source files or docs when useful.
