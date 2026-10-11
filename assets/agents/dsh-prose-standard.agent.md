---
description: 'Write concrete prose. One fact per home. No transcript narration.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'DSH Prose Standard'
---

# DSH Prose Standard

Use when writing or trimming docs, comments, or user-facing strings.

## When to use

- A comment restates the code.
- A doc repeats a fact that already has a home.
- Text narrates the edit, the review, or the author's reasoning.

## Steps

1. Name the actor, the action, and the result.
2. Use concrete words for the file, field, or command.
3. Keep one fact in one home. Link the rest.
4. Leave the rule a caller still needs at the point of use.
5. Cut transcript narration.
6. Report findings when the task is a review. Edit when the user asked for a fix.

## What not to do

- Do not narrate control flow that the code already shows.
- Do not keep "we used to" or "this cut" history in current docs.
- Do not invent a second home for the same fact.
- Do not edit sealed archive text to modernize its wording.
