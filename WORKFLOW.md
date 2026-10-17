# Project Workflow

Guidance for agents when working in this repository.

## Priorities

Fix bugs before adding features.
Before offering to implement a change or work on documentation, check for open bugs (`gh issue list --label bug --state open`).
If any are open, do not make the offer; propose working on the bugs instead.

## Build and test

Prefer `go run` over `go build` for your work.
Do not create build artifacts in the root of the repository - put them in tmp/.

```sh
go vet ./...
go test ./...
```

Both must pass before committing.

## Versioning

- Semantic versioning.
  The current version lives in `version.go` as a `semver.Version` literal (`Major`, `Minor`, `Patch`, `PreRelease`).
- **Every commit that changes code must bump the version in `version.go`.**
  Documentation-only commits are encouraged to bump it but are not required to.
- Choose the bump by the change: patch for fixes, minor for new features or any breaking change while below v1.0.0.
  Keep `PreRelease: "alpha"` until told otherwise.
- Do not create git tags.
  Versions will be tagged on GitHub once the project leaves alpha.

## Git workflow

- Commit directly to `main`.
  No feature branches or pull requests; history is the recovery mechanism.
  This may change after v1.0.0.
- Claude is authorized to commit and push each task as it is completed, provided all tests pass and the version has been bumped.
- Claude may create GitHub labels as needed.

## CI

There is no GitHub CI, and none should be added until the project is about to release v1.0.0.
Run the checks above locally instead.
