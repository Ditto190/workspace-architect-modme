---
description: 'Apply Clerk auth standards. Document env var names only. Never print secrets.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'Clerk Auth Standards'
---

# Clerk Auth Standards

Use when code touches Clerk sign-in, sessions, or keys.

## When to use

- A route or page checks a Clerk session.
- Someone hardcoded a key or logged a token.
- Docs need to name Clerk environment variables.

## Steps

1. Read the framework and the existing auth entry point.
2. Client code reads `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY`.
3. Server code reads `CLERK_SECRET_KEY` from the environment.
4. Document those env var names only.
5. Never print secrets.
6. Reject wildcard session trust and unsigned client-only checks on protected routes.

## What not to do

- Do not paste key values, tokens, or webhook signing secrets.
- Do not echo `process.env` dumps.
- Do not commit `.env` files.
- Do not invent a second auth provider beside Clerk for the same route.
