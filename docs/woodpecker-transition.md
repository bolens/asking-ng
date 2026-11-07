# Woodpecker automation

The shared native pipeline runs the existing source lint, Spec Kit integrity,
actionlint and offline zizmor contracts through `bash scripts/ci/check-fleet.sh`.
The tooling revisions, checksummed actionlint and security thresholds match the
previous hosted checks. Keep the native current-head status required in branch
protection, and verify the genuine merged-main pipeline after delivery.

## CI organization

The [shared purpose phases](https://github.com/bolens/.github/blob/main/docs/woodpecker-transition.md#ci-organization)
describe repository automation here. Product behavior, a product test suite and
product publication remain unspecified.

| Phase | Check group / canonical local command | Native workflow / step | Retained hosted owner / boundary |
| --- | --- | --- | --- |
| `validate` | Complete Linux automation gate: `bash scripts/ci/check-fleet.sh` | `woodpecker` / `fleet-contracts` | PR, main push and native manual execution; Linux/amd64 tooling downloads are pinned and invocation-owned |
| `validate` | Focused workflow checks: `actionlint`; `zizmor --offline --min-severity medium --min-confidence medium .github` | Included in the same fleet helper | Manual hosted validation fallbacks retain their current entrypoints |
| `test` | Development-image tooling: `bash .devcontainer/smoke.sh` inside the built devcontainer | Separate from native policy checks | Hosted Devcontainer builds the actual image and runs post-create setup when selected or manually requested |

The full helper reuses the existing pinned source and Spec Kit validators; it
requires the documented CI tools and network access for temporary downloads.
Use [the devcontainer guide](../.devcontainer/README.md) for that environment.
The native identity, protected check and hosted metadata/update authority remain
unchanged.

GitHub retains manual validation fallbacks, scheduled/explicit Spec Kit updates,
metadata assignment, and actual Docker devcontainer acceptance. A selected
container change builds the actual Dockerfile and runs setup smoke with a
read-only root filesystem, no network, and the runner UID. The setup checkout
remains writable. Native tooling checks alone do not prove a container builds.

The container images are immutable. Review Woodpecker image pins and helper
tooling revisions monthly and after security releases; existing dependency
automation does not discover them. The retained GitHub action references have
weekly grouped Dependabot monitoring; actual update execution is separate evidence.
Updates need a reviewed PR and genuine native evidence. Recover by corrective or
revert PR. This repository has no product runtime or versioned artifact release.
