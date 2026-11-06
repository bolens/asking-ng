# Woodpecker automation validation

Run workflow syntax/security, selected source lint, and managed Spec Kit integrity
on the shared Woodpecker site for pull requests, main pushes, and manual checks.
This repository has no product runtime or product test suite.

Use the same immutable tooling revisions and security thresholds as the existing
hosted checks. Fail on failed producer commands. Contributor code receives no
publication credentials, privileged mode, host socket, or host Nix store.
Retire duplicate hosted checks only after genuine native PR and main success.
Keep GitHub metadata assignment and scheduled updater workflows on GitHub.
