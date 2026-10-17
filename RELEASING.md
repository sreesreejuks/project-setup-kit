# Releasing

> Adapt this guide to the project's release process before using it.

## Before a release

- [ ] Confirm the release branch and working tree are in the expected state.
- [ ] Review merged changes and determine the version impact.
- [ ] Run the required checks:

  ```sh
  [TODO: lint command]
  [TODO: test command]
  [TODO: build command]
  ```

- [ ] Review dependency, migration, and compatibility changes.
- [ ] Update user-facing documentation and release notes.

## Versioning

[TODO: Describe the versioning scheme, such as Semantic Versioning, and how a
change maps to major, minor, or patch.]

## Release steps

1. [TODO: Prepare or merge the release changes.]
2. [TODO: Create the version tag or run the release tool.]
3. [TODO: Publish artifacts or deploy.]
4. [TODO: Verify the release and deployment.]
5. [TODO: Communicate the release.]

If using automated releases, document the required branch, credentials,
permissions, and dry-run command here. Never paste tokens or secrets into this
file.

## Rollback

[TODO: Document how to roll back the deployment or withdraw a release, including
who to contact and how to communicate the rollback.]
