---
description: 'Land a same-repo PR stack through the native stack merge. Do not merge children by hand.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'DSH Merging Stacked PRs'
---

# DSH Merging Stacked PRs

Use when dependent pull requests must land in order.

## When to use

- PRs form a stack: each branch is based on the one below.
- The user asks to merge stacked or dependent PRs.
- A PR's base is another open PR in the same repository.

## Steps

1. Confirm the official stack command is available.
2. Read each PR's number, base, head, and stack membership.
3. Require one native stack in the same repository.
4. Land with the stack merge operation, bottom to top.
5. Check that each included PR merged at the reviewed head.
6. Delete branches only after the whole stack has landed.

## What not to do

- Do not merge a child into its parent branch with a one-off merge.
- Do not retarget PRs by hand to imitate a stack.
- Do not delete a branch while a later PR in the stack is open.
- Do not cross a fork boundary with this flow.
