---
description: 'Initialize git only when the directory is not already a repository.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'Speckit Git Initialize'
---

# Speckit Git Initialize

Use when a project needs git and may not have it yet.

## When to use

- The directory has no `.git`.
- A spec-kit checkout should be initialized.
- You are unsure whether git is already present.

## Steps

1. Look for `.specify/extensions/git/scripts/bash/initialize-repo.sh`.
2. On Windows, look for the PowerShell script beside it.
3. If that repo script is present, run it. Stop after it finishes.
4. If the script is absent, run `git rev-parse --is-inside-work-tree`.
5. If that succeeds, stop. The directory is already a repo.
6. If it is not a repo, run `git init` only.
7. Never re-init.

## What not to do

- Do not run `git init` inside an existing repository.
- Do not delete `.git`.
- Do not invent a second initial commit when the script already made one.
- Do not change remotes or history.
