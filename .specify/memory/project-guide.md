# asking-ng project guide

[Documentation](../../docs/README.md)

Only repository automation is implemented. Product requirements, runtime, and public API are not established.

## Current source and ownership

`README.md` records the bootstrap state. `.github/workflows/auto-assign.yml`
assigns issue/PR metadata through the shared fleet workflow.
`.github/workflows/workflow-checks.yml` validates workflow syntax and security.
`RELEASING.md` owns delivery; there are no product packages or version tags.

## Decisions and acceptance

Choose the first user-facing behavior, data ownership, interfaces, and supported runtime in a reviewed feature specification before adding implementation. Record the intended user, observable success and failure cases,
compatibility, storage boundaries, and external authority. A product test
command cannot be documented until its actual toolchain exists.

## Current validation

Run `actionlint`,
`zizmor --offline --min-severity medium --min-confidence medium .github`, and
`git diff --check`. The Spec Kit workflow additionally checks this integration.
These are repository-automation checks; product coverage remains unimplemented.
Keep real credentials and user data out of specifications and fixtures.

## Spec Kit workflow

Create feature specifications only for new work. Record observable acceptance
criteria in `spec.md`, source ownership and constitution checks in `plan.md`,
and executable verification in `tasks.md`. Resolve material unknowns before
implementation. Mark tasks complete only with evidence and retain completed
feature directories as decision history.

Managed templates, scripts, and Codex skills belong to their integration
manifests. Customize this guide and the constitution; do not hand-edit managed
files or hashes. Verify project-owned memory survives regeneration. The pinned
Spec Kit workflow validates integration metadata, managed hashes, constitution
metadata, and Bash syntax. Follow `RELEASING.md` for delivery.
