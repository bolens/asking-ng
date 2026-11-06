# Woodpecker automation

The shared native pipeline runs the existing source lint, Spec Kit integrity,
actionlint and offline zizmor contracts through `bash scripts/ci/check-fleet.sh`.
The tooling revisions, checksummed actionlint and security thresholds match the
previous hosted checks. Keep the native current-head status required in branch
protection, and verify the genuine merged-main pipeline after delivery.

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
