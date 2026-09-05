# Delivery playbook

This repository currently contains repository automation and has no versioned
artifacts. The initial commit establishes the default branch so later changes
can use pull requests.

For workflow changes, run `actionlint`,
`zizmor --offline --min-severity medium --min-confidence medium .github`, and
`git diff --check`. Review the complete diff and publish a focused feature branch
with `git push --set-upstream origin HEAD`. Open a PR against `main`, verify
applicable current-head checks and review conversations, then squash-merge.
Never bypass protection or force-push. Verify the merged workflow and delete
only the verified merged feature branch.

Follow the [fleet playbook](https://github.com/bolens/.github/blob/main/RELEASING.md).
Repair automation through a corrective or revert PR. Disabling the assignment
workflow stops future assignment without removing existing assignees. Add a
product-specific release process when the repository gains deliverable artifacts.

## Branch protection

The default branch requires pull requests, resolved conversations, linear
history, and an up-to-date branch with passing required checks, including `lint
/ actionlint` and `lint / zizmor`. These rules also apply to administrators;
force pushes and branch deletion are disabled. Zero approving reviews are
required because this is a solo-maintainer repository; review the complete diff
before merging.

Keep required checks available on every pull request. Filter expensive work
inside jobs or use an always-running result job that rejects failures and
cancellations. Update the protection settings when renaming required jobs.

## Source lint

The Source lint workflow checks maintained markdown files selected by
[`.github/source-lint.json`](.github/source-lint.json) on every pull request
and push to `main`. Existing native checks remain part of the merge gate.
Use the [shared local reproduction instructions](https://github.com/bolens/.github/blob/7603518f305fb76f7bb1b9979f2692521f633b82/docs/source-lint.md)
with the same tooling revision pinned in
[the workflow](.github/workflows/source-lint.yml). Review exclusions when adding
source files; generated and imported files retain their native validation.
Require the new check to pass on the current PR head before merging.
