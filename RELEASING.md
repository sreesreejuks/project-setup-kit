# Releasing

This repository uses [Semantic Versioning](https://semver.org/) and
automatically publishes GitHub Releases and updates [CHANGELOG.md](./CHANGELOG.md)
from Conventional Commits merged into `main`.

## Commit messages

Use the Conventional Commits format:

```text
<type>(optional scope): <summary>
```

Examples:

- `feat: add a container setup checklist` — minor release
- `fix: clarify the dependency audit guidance` — patch release
- `docs: improve the project setup instructions` — patch release
- `feat!: replace the release workflow` — major release
- `docs: change the repository conventions` with a `BREAKING CHANGE: ...`
  footer — major release

Signal breaking changes with `!` after the type or a `BREAKING CHANGE: ...`
footer. Commits that do not affect the published guidance or release process,
such as `chore:` changes, do not trigger a release unless they contain a
breaking-change marker. Use a Conventional Commit as the squash-merge title so
the release workflow can determine the version.

## Versioning

- **Major (`X.0.0`)**: incompatible changes to the guidance or repository
  conventions; signal with `!` or a `BREAKING CHANGE:` footer.
- **Minor (`x.Y.0`)**: a new capability or substantial new guidance, using
  `feat:`.
- **Patch (`x.y.Z`)**: corrections and improvements to existing guidance,
  using `fix:` or `docs:`.

The workflow creates tags in the `vX.Y.Z` format. No release is made for a
change that does not match a release-triggering commit.

## Automated release process

1. Merge changes into `main` using a Conventional Commit title.
2. GitHub Actions analyzes commits since the previous release.
3. When a release is warranted, the workflow updates `CHANGELOG.md`, commits the
   generated entry, creates a `vX.Y.Z` tag, and publishes a GitHub Release.

The workflow uses the automatically provided `GITHUB_TOKEN` with repository
contents write permission. Do not add a personal access token or store tokens in
the repository. Releases are not published from pull requests.

## Rollback

Do not move or delete a published version tag. If a release needs correction,
make and merge a follow-up fix so the automated workflow publishes a new patch
release. If a release must be withdrawn, unpublish its GitHub Release while
retaining the tag, and document the reason in the next release.
