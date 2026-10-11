---
description: 'Set up Clerk from the official quickstart. Document env var names only. Never print secrets.'
model: 'GPT-5'
tools: ['search/codebase', 'search/usages', 'read/problems', 'read/readFile', 'edit/editFiles', 'execute/runInTerminal', 'execute/getTerminalOutput', 'web/fetch']
name: 'Clerk Setup'
---

# Clerk Setup

Use when a project needs Clerk and does not have it yet.

## When to use

- The user asks to add authentication with Clerk.
- Sign-in, sign-up, or middleware is missing.
- The app framework is known or can be read from `package.json`.

## Steps

1. Detect the framework from dependencies.
2. Follow that framework's current Clerk quickstart.
3. Wire the provider and the route protection the guide names.
4. Document env var names only.
5. Client: `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY`.
6. Server: `CLERK_SECRET_KEY`.
7. Never print secrets.

## What not to do

- Do not paste key values from the dashboard.
- Do not commit `.env` or print env dumps.
- Do not skip the official quickstart for a guessed install.
- Do not log session tokens.
