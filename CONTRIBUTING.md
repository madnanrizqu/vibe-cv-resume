# Contributing

## Branch Naming

Branches must follow this pattern:

```
<type>/<issue-number>/<short-description>
```

Examples:
- `feat/12/add-skills-section`
- `fix/7/fix-font-rendering`
- `chore/11/init-release-system`
- `docs/3/update-quickstart`

A GitHub Actions check on every PR validates this format and links the PR to the issue automatically.

## Workflow

1. Open an issue describing the change
2. Create a branch following the naming convention above
3. Open a PR — the check will comment the linked issue automatically

## Releases

Releases are tagged manually by the maintainer. When a tag matching `v*.*.*` is pushed, GitHub Actions creates a release with auto-generated notes from commits since the last tag.
