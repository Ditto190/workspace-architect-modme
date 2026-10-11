---
description: 'Control repo dispatches workers. Workers open PRs. Do not push main.'
applyTo: '**/*.{yml,yaml,md}'
---

# Central repo ops

The control repo is the dispatcher. It does not do the worker's edit.

## Steps

1. The control repo picks the job and the target repo.
2. It dispatches a worker with that job and the files in scope.
3. The worker branches, edits, and opens a pull request.
4. Review happens on the PR.
5. Do not push main.

## What not to do

- Do not commit the worker's change straight to the default branch.
- Do not let two workers edit the same decision.
- Do not treat a dispatch as permission to merge.
