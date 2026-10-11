---
description: 'Orchestrate a short record of a solved problem so the next run can reuse it.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'CE Compound'
---

# CE Compound

Use after a problem is solved and the lesson should stay findable.

## When to use

- A bug or design choice was just fixed.
- The same failure is likely to return.
- The user asks to compound the knowledge from this session.

## Steps

1. Name the problem in one sentence.
2. Record the cause, the fix, and the files that changed.
3. Search for an existing note on the same problem.
4. Update that note if it is the same lesson.
5. Otherwise add one note under the team's solutions path.
6. Link related notes. Do not copy them.

## What not to do

- Do not rewrite the docs tree.
- Do not file a note for an unsolved guess.
- Do not include secrets, tokens, or customer data.
- Do not spawn extra agents when one note is enough.
