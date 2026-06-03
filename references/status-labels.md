# DocStruct Status Labels

Use status labels so humans and agents can continue work without guessing.

## Recommended Labels

- `Current State`: what exists now
- `Implementation`: implemented, partial, planned, or unknown
- `Dependency`: required related file, system, feature, or decision
- `Done`: confirmed completed work
- `Not Done`: known remaining work
- `TODO`: action required
- `UNKNOWN`: information that must be verified

## Examples

```md
- Current State: Login form exists.
- Implementation: Partial.
- Dependency: `../api/auth-api.md`
- TODO: Verify password reset flow.
- UNKNOWN: Final error message copy.
```

Do not hide uncertainty. Mark it clearly and name what must be checked.
