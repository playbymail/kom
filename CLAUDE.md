# CLAUDE.md

## Project Overview

This repository is `kom` (module `github.com/playbymail/kom`), a Go implementation of Koyore O'er Ablonar,
based on The Keys of Medokh (KoM), a play-by-mail fantasy strategy game.
The project is at its very start: the only code is the `kom` package's `version.go`.

Licensed AGPL-3.0-or-later.
New Go files start with the same two-line header as `version.go`:

```go
// Copyright (c) 2026 Michael D Henderson.
// SPDX-License-Identifier: AGPL-3.0-or-later
```

## Workflow

Follow [WORKFLOW.md](WORKFLOW.md). In short:

- Check open bugs (`gh issue list --label bug --state open`) before offering features or documentation work; propose bugs first.
- `go vet ./...` and `go test ./...` must both pass before committing.
- Prefer `go run` to `go build`; build artifacts go in `tmp/`, never the repository root.
- Every commit that changes code bumps the version in `version.go` (patch for fixes, minor for features or breaking changes below v1.0.0).
  Keep `PreRelease: "alpha"`. Do not create tags.
- Commit and push directly to `main` once a task is done and checks pass. No branches, no PRs, no CI.

## Reference Material: `../medocs`

The sibling repository `../medocs` holds the game's original documentation.
It is **read-only reference** — never modify it.
Its own `CLAUDE.md` describes its layout in detail.

Use the curated edition in `../medocs/docs/`:

| Path                             | Contents                                                                      |
|----------------------------------|-------------------------------------------------------------------------------|
| `docs/manual/`                   | Dynamic Games rule compendium (post-1996), one file per topic                 |
| `docs/manual/orders/`            | Orders by group; `summary.md` lists every order code                          |
| `docs/manual/tables/`            | Tribe, god, map, and construction-cost tables                                 |
| `docs/sheets/`                   | Talisman Games rule sheets (1993–94), one per original; `README.md` indexes by topic |
| `docs/reconstructed/`            | Material written to replace lost originals — not authoritative                |

`../medocs/sources/` holds the unmodified originals and `../medocs/converted/` the raw machine conversions;
consult them only to check the curated text.

Things to keep in mind when implementing rules from these documents:

- The two sources come from different eras of the game and sometimes disagree.
  Note which source a rule comes from, and raise conflicts with the user rather than silently picking one.
- The original game was unfinished: magic, religion, spell research, and detailed combat and siege rules are missing,
  and the end game may not work. Treat gaps as gaps — ask before inventing rules to fill them.
