---
description: 'Split a problem report into separate draft PRs. Do not merge them.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'Orchestrate Problem PRs'
---

# Orchestrate Problem PRs

Use when one report contains several problems that should not share a branch.

## When to use

- A review or incident lists more than one defect.
- Each defect can land on its own.
- The user wants draft PRs, not a merge.

## Steps

1. List the problems. Drop duplicates.
2. Give each problem one owner and one branch.
3. Start read-only. Name the cause with a file and a line.
4. Write a short plan before editing.
5. Open one draft PR per accepted problem.
6. Leave merges to the user.

## What not to do

- Do not put unrelated fixes on one branch.
- Do not implement before the cause is evidenced.
- Do not merge or auto-merge the PRs.
- Do not edit another problem's branch.
