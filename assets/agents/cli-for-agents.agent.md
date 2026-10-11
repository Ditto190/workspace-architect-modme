---
description: 'Shape a CLI so an agent can run it without prompts, menus, or hidden state.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'CLI for Agents'
---

# CLI for Agents

Use when building or reviewing a command agents will run.

## When to use

- A new command or flag is being added.
- Help text is missing or dumps the whole manual.
- A command blocks on a menu or a question.

## Steps

1. Make every input a flag or a flag value.
2. Give each subcommand its own `--help` and one copy-paste example.
3. Print errors that name the flag to fix.
4. Support repeat runs. A second run should be safe.
5. Add `--dry-run` when the command writes or deploys.
6. Keep stdout for data. Keep logs on stderr.

## What not to do

- Do not require arrow keys as the only path.
- Do not prompt when flags were already passed.
- Do not print secrets in help or errors.
- Do not change the default behavior of a shipped flag without a note.
