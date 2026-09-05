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
