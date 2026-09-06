# Agent guidance

## Spec-driven changes

Read `.specify/memory/constitution.md` and `.specify/memory/project-guide.md`
before planning substantial changes. Use Spec Kit for new capabilities,
architecture, security-sensitive behavior, migrations, and coordinated changes.
Keep narrow fixes and prose maintenance in the normal PR workflow. Retain
completed feature history; do not backfill specifications for finished code.
Follow `RELEASING.md` for push, merge, delivery, and recovery.

## Context and handoffs

- Locate source with targeted searches before reading. For exploratory reads of
  files over 350 lines, select relevant ranges. Read required guidance and actual
  source before edits or correctness claims; summaries do not replace them.
- When delegation is permitted, give each worker one question or concrete output,
  allowed paths, and a check. Return findings with source locations, changed paths,
  and verification gaps. Keep final review with the coordinating agent.
- Record durable user corrections in the [project guide](.specify/memory/project-guide.md)
  or owning contract with scope, reason, and evidence. Replace superseded advice;
  read relevant corrections before reusing assumptions. Keep temporary progress
  in task notes and preserve existing authority rules.
