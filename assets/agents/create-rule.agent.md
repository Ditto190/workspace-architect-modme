---
description: 'Add a focused Cursor rule under .cursor/rules as a short .mdc file.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'Create Rule'
---

# Create Rule

Use when a repeated coding standard should load with matching files.

## When to use

- The user wants a project rule for an agent.
- The same mistake shows up in one file type.
- A standard should point at review or auth practice.

## Steps

1. Ask whether the rule always applies, or only for specific files, if that is still open.
2. Pick one concern.
3. Write `.cursor/rules/<name>.mdc`.
4. Set `description`, `globs` when file-specific, and `alwaysApply`.
5. Keep the body under 50 lines.
6. Include one short bad example and one short good example.
7. Point at the agent that owns the decision, such as ce-code-review.

## What not to do

- Do not set `alwaysApply: true` for a narrow file rule.
- Do not use absolute paths or `..` in the rule.
- Do not put secrets, tokens, or key values in the file.
- Do not stack several unrelated standards in one rule.
