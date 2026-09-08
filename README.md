# Org DevOps Tools policy center

This repository is the organization-level source for shared community policies used by repositories in `Org-DevOps-Tools`.

## Shared policies

- [Contribution guidelines](CONTRIBUTING.md)
- [Code of Conduct](CODE_OF_CONDUCT.md)
- [Security policy](SECURITY.md)
- [Policy centralization proposal](POLICY-CENTRALIZATION-PROPOSAL.md)
- [Policy pointer automation](POLICY-AUTOMATION.md)

Repositories may provide local supplements when their build process, security scope, release process, or legal obligations differ. Repository-specific `LICENSE` and `NOTICE` files remain authoritative and are not replaced by this repository.

## Policy pointer automation

The workflow in `.github/workflows/sync-policy-pointers.yml` can open pull requests in organization repositories that do not yet contain `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, or `SECURITY.md`. It only creates missing files and never overwrites an existing policy.

Before enabling the workflow, create an organization-scoped secret named `ORG_POLICY_SYNC_TOKEN`. The token must be limited to the required organization repositories and have permission to read repository metadata, create branches, write contents, and create pull requests. Run the workflow manually first to review the generated pull requests, then retain the weekly schedule for newly created repositories.