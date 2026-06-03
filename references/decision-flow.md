# DocStruct Decision Flow

Use this flow before creating or changing documentation.

1. Read the root README and existing docs.
2. Check whether the requested information already has a responsible file.
3. If it exists, update that file.
4. If multiple files repeat the same fact, keep one source and replace copies with links.
5. If no file owns the information, decide whether future agents or maintainers need it.
6. If yes, create the smallest useful file.
7. If no, leave it undocumented.
8. Mark missing or uncertain details as `TODO` or `UNKNOWN`.

Prefer fewer files with clear ownership over many files with overlapping responsibilities.
