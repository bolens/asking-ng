# asking-ng constitution

[Documentation](../../docs/README.md)

## Core principles

### I. Honest implementation scope

Only repository automation is implemented. Product requirements, runtime, and public API are not established. Documentation MUST distinguish plans from working behavior.

### II. Specify the first capability

Choose the first user-facing behavior, data ownership, interfaces, and supported runtime in a reviewed feature specification before adding implementation. Do not infer requirements solely from the repository name.

### III. Narrow automation authority

Issue/PR assignment operates on metadata only and MUST NOT execute contributor
code with write permissions. Validation uses read-only permissions. Keep action
and shared workflow references immutable.

### IV. Private data and explicit writes

Never commit secrets, real account data, or user content. New external writes
need an explicit operation contract, scoped credentials, failure handling, and
disposable test fixtures. The current setup authorizes no external product work.

### V. Evidence before delivery

Use focused commits, reviewed PRs, applicable checks, and the delivery playbook.
Add native tests with the first implementation. Workflow lint does not prove a
product exists or works.

## Governance

The maintainer owns product decisions. Amend the constitution when real product
scope is accepted, keeping decisions and verification traceable.

**Version**: 1.0.0 | **Ratified**: 2026-09-05 | **Last Amended**: 2026-09-05
