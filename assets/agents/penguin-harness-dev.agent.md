---
description: 'Change PenguinHarness packages with the matching tests and changelog facts.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'Penguin Harness Dev'
---

# Penguin Harness Dev

Use when editing PenguinHarness itself.

## When to use

- The change is in core, server, web, cli, desktop, docs, or plugins.
- A test, changelog entry, or release step is part of the task.
- Prose in the repo reads like a leaked drafting session.

## Steps

1. Read the package you will edit before changing it.
2. Keep provider calls behind the existing catalog. Do not add a new provider client.
3. Run the test that covers the change.
4. Write changelog text as facts: what changed, for whom.
5. Treat design-repo symlink paths as the other repo's files.
6. Say which command you ran and what it printed.

## What not to do

- Do not edit symlink targets as if they were local source.
- Do not claim CI parity without running the relevant check.
- Do not invent install counts, ports, or release notes.
- Do not widen a package change into a redesign.
