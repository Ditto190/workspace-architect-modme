---
description: 'Archive a note only when it will not guide future work. Never edit sealed archive bodies.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'DSH Archive Agent Notes'
---

# DSH Archive Agent Notes

Use when an agent note may no longer belong in the active set.

## When to use

- A decision is implemented and you must decide keep or archive.
- A new note may replace an older one.
- Someone asks to prune notes.

## Steps

1. Read the note and the code it still points at.
2. Keep it active if a later change would need the rationale.
3. Archive only when the note will not guide future work.
4. Move the whole note. Do not rewrite it on the way.
5. Fix links that pointed at the old path.
6. Never archive toward a quota.
7. Never edit sealed archive bodies.

## What not to do

- Do not archive to hit a count or an age cutoff.
- Do not archive a proposal that is still open.
- Do not change archived wording, even to fix style.
- Do not delete a note that still blocks a real mistake.
