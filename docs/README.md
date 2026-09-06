# Documentation

Repository automation and the boundary before product implementation.

## Start here

| Need | Owning document |
| --- | --- |
| Use the project | [README.md](../README.md) |
| Change the repository | [AGENTS.md](../AGENTS.md) |
| Deliver or recover | [RELEASING.md](../RELEASING.md) |
| Plan substantial changes | [.specify/memory/project-guide.md](../.specify/memory/project-guide.md) |
| Non-negotiable constraints | [.specify/memory/constitution.md](../.specify/memory/constitution.md) |

## Architecture

Only repository automation is implemented. No product runtime, API, or architecture has been
accepted. The [project guide](../.specify/memory/project-guide.md) owns the decisions required for
the first capability. Do not infer a product design from the repository name.

## Deployment and recovery

[RELEASING.md](../RELEASING.md) owns delivery of repository automation. There is no application
deployment, package, or versioned artifact. Workflow lint verifies automation only.

## Database and state

There is no product database or storage contract. Establish data ownership, retention, interfaces,
and external authority with the first feature specification before introducing persistence.

## Documentation maintenance

Keep decisions, invariants, failure modes, and recovery requirements in the owning document. Link to
commands, defaults, schemas, and generated catalogs instead of copying them. Change the owner and
affected references together. Update this index when adding or moving a guide, and verify relative
links and heading anchors. Historical specs and audits describe their recorded revision, not current
runtime proof. A topic without an implementation stays explicitly unimplemented.
