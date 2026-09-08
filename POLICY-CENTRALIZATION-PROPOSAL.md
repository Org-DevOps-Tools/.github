# Central Policy Proposal

## Decision

Use `Org-DevOps-Tools/.github` as the organization-level source for policies that repeat across repositories. GitHub can use these files as default community-health files when a repository does not provide its own version.

## Ownership model

| Artifact | Central organization repository | Individual app or library repository |
| --- | --- | --- |
| `CONTRIBUTING.md` | Default contribution, review, and secret-handling rules | Local build, test, release, and deployment supplement |
| `CODE_OF_CONDUCT.md` | Single authoritative community standard and reporting route | No duplicate unless a repository has an approved localized requirement |
| `SECURITY.md` | Common reporting and safe-research baseline | Local scope, supported versions, hosted-service ownership, and contact details |
| `LICENSE` / `LICENCE.md` | No organization-wide replacement | Complete authoritative license text for that repository |
| `NOTICE` | No organization-wide replacement | Required copyright and third-party attribution for that distribution |

## License assessment

Applications and libraries can have different licenses. Therefore licenses are deliberately excluded from organization-level inheritance:

- Each repository declares its own SPDX license identifier and retains the complete license text under its chosen filename, such as `LICENSE.txt` or `LICENCE.md`.
- A repository's license covers only the work to which it applies; it does not erase module-level or third-party license notices.
- `NOTICE` files and third-party license texts remain with the application or library distribution when required.
- CI may validate license metadata, required legal files, and approved transitions, but must not generate or replace legal text from this repository.
- Legal review is required before changing an application's or library's declared license.

## POC rollout

1. Keep the shared policy files in this repository and review them quarterly.
2. Add a small local supplement only where repository context is required.
3. Add a repository-level catalog recording central policy adoption and local exceptions.
4. Pilot the model with one application and one library.
5. Add CI checks for policy links, local security scope, SPDX metadata, and required notices.

## Acceptance criteria

- Maintainers can find the authoritative shared policy in this repository.
- A repository with EUPL, Apache, MIT, or another approved license can adopt the shared policies without changing its legal files.
- Security guidance remains accurate for source code, applications, and hosted services.
- Local supplements are additive and do not silently diverge from the organization baseline.