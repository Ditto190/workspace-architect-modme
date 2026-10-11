---
description: 'Find a few evidence-backed cuts. Do not delete behavior that still has a consumer.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'DSH Find Simplifications'
---

# DSH Find Simplifications

Use when code, config, or tests look heavier than the behavior they serve.

## When to use

- A module has no caller.
- Two paths do the same job.
- The user asks what can be removed, not what can be added.

## Steps

1. Lock the scope. Do not scan the whole repo unless asked.
2. Search for producers and consumers of the symbol.
3. Record what disappears, what remains, and why it might stay.
4. Prefer a few cuts you can show.
5. Implement only when the user asks.
6. Leave seams that still have a real consumer.

## What not to do

- Do not delete code because it looks unused after one search.
- Do not count deletions as success.
- Do not remove a protected product path to make a diff smaller.
- Do not mix a simplification with a new feature.
