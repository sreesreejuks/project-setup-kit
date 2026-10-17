# New Project Setup Checklist

Use this checklist when starting a project to keep development reproducible,
catch problems early, and make releases predictable.

## Development environment

- [ ] Declare the supported runtime and package-manager versions.
- [ ] Add a VS Code Dev Container so tools and project dependencies stay out of
  the host OS.
- [ ] Pin the container runtime version; install dependencies from the lockfile
  (`npm ci` for npm projects).
- [ ] Keep container dependencies in a container volume rather than sharing
  host `node_modules`.
- [ ] Forward the development server port and document how to start and open the
  app.
- [ ] Add the useful editor extensions and project settings to the container
  configuration.

## Quality checks

- [ ] Add linting and formatting commands early.
- [ ] Run lint, type checks, tests, and a production build in CI.
- [ ] Fix lint errors instead of suppressing rules without a clear reason.
- [ ] Review existing warnings and decide which are acceptable or should be
  addressed.
- [ ] Validate CI commands locally before relying on them in pull requests.

## Dependencies

- [ ] Commit the package-manager lockfile and use lockfile-based installs in
  development and CI.
- [ ] Check that related tooling packages support compatible versions of their
  shared dependencies.
- [ ] Run relevant commands after dependency changes (for example, lint, build,
  and release dry-run).
- [ ] Review dependency audit output; avoid broad or forceful upgrades without
  assessing their impact.

## Releases

- [ ] Choose a versioning strategy and document the release process.
- [ ] If using semantic-release, define the release branches, commit rules,
  release-note preset, changelog, and GitHub release behavior.
- [ ] Keep changelog preset and writer versions compatible; verify this with a
  dry run.
- [ ] Configure CI credentials with the minimum permissions required to publish
  releases and tags.
- [ ] Run release dry-runs before enabling automated publishing.

## Documentation and repository hygiene

- [ ] Document prerequisites, first-time setup, development commands, tests,
  and production build/deploy steps.
- [ ] Explain how to use the Dev Container and any required host tools, such as
  Docker and the VS Code extension.
- [ ] Keep development-container configuration separate from production
  deployment configuration.
- [ ] Add a suitable `.gitignore`; do not commit generated output, local
  dependencies, or secrets.
- [ ] Verify a fresh clone can install, run checks, build, and start following
  only the documented instructions.
