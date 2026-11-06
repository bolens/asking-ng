# Plan

Use a digest-pinned Node container and a portable helper that fetches exact
fleet source-lint and Spec Kit revisions. Install the same pinned Ruff, zizmor,
and checksummed actionlint selected by those workflow contracts. Scratch tooling
clones and package state are temporary and removed on exit.

Read the full source/helper contract, run workflow/security/shell checks, then
verify genuine current-head PR and merged-main pipelines. Update protection only
after verified native contexts exist. Recover through a corrective or revert PR.
The constitution's automation-only scope and read-only credential boundary hold.
