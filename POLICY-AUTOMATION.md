# Policy pointer automation

The `sync-policy-pointers.yml` workflow creates pull requests containing missing `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, and `SECURITY.md` files in repositories belonging to `Org-DevOps-Tools`.

The generated files are pointers to the policy center in this repository. The workflow never overwrites an existing policy file, so a repository can retain an approved local supplement or exception. Maintainers approve and merge the pull requests.

## Required setup

Create an organization secret named `ORG_POLICY_SYNC_TOKEN`. Use a GitHub App installation token where possible. The installation must be able to list organization repositories and write repository contents. A fine-grained personal access token can be used for the POC if organization policy permits it; limit it to the required repositories and rotate it regularly.

The workflow runs weekly and can also be started from **Actions > Sync organization policy pointers > Run workflow**. The repository token is intentionally not used for cross-repository writes because its permissions do not automatically grant access to every organization repository.

## License boundary

This automation creates policy pointers only. It does not create, modify, or centralize `LICENSE`, `LICENCE.md`, or `NOTICE` files. Every application and library must continue to declare and distribute its own applicable license and third-party notices.