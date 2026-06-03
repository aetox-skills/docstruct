# Audit Project Documentation Prompt

Use DocStruct to audit the existing project documentation.

## Instructions

Inspect the repository documentation and check for:

- duplicated content
- unclear file responsibility
- missing status
- outdated information
- API details outside API docs
- database details outside database docs
- frontend/backend logic mixed together
- over-documentation
- missing README files
- unclear next steps

## Output Required

Return:

- critical issues
- duplicated areas
- files to merge
- files to split
- files to shorten
- missing documents
- outdated or uncertain information
- recommended next actions

## Constraints

- Recommend the smallest useful documentation structure.
- Prefer updating and merging over creating new files.
- Mark uncertainty as `UNKNOWN`.
- Mark required work as `TODO`.
- Do not invent missing details.
- Do not recommend a documentation website unless the project clearly needs one.
