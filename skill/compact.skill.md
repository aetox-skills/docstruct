# Compact DocStruct Skill

## Purpose

Help an AI agent create or update project documentation with minimal duplication and low token cost.

## 10 Compact Rules

1. Read existing docs before writing.
2. Update existing files before creating new files.
3. Create a file only when it has a clear responsibility.
4. Keep one source of truth for each fact.
5. Link instead of copying.
6. Keep docs short by default.
7. Expand only when complexity requires it.
8. Mark missing details as `TODO` or `UNKNOWN`.
9. Do not invent implementation details.
10. Remove decorative or low-value documentation.

## Simple Decision Flow

1. If the information already has a responsible file, update that file.
2. If the information is repeated, keep the best source and replace copies with links.
3. If the information is useful but has no home, add the smallest useful file.
4. If the information is uncertain, mark it `UNKNOWN` and state what to verify.
5. If the information does not help future work, leave it out.

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

## Final Rule

Write less, but make the next step clear.
