---
description: 'Coding standards for strategy interviews, git init, Cursor rules, code review, and Clerk env names.'
applyTo: '**/*.{ts,tsx,js,md,mdc}'
---

# Coding standards

Use these rules when editing application code, docs, or Cursor rules.

## Strategy

Ask the user one section at a time. Do not invent `STRATEGY.md`. Write only answers the user gave.

## Git

If `.specify/extensions/git/scripts/bash/initialize-repo.sh` exists, run it. Otherwise run `git init` only when the directory is not already a repo. Never re-init.

## Cursor rules

Put rules in `.cursor/rules/*.mdc`. One concern. Under 50 lines. Set `alwaysApply` only for a universal rule.

## Review

Use the ce-code-review agent to report findings. Do not auto-merge.

## Clerk

Read the publishable key from `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY`. The server secret env var name is `CLERK_SECRET_KEY`. Document env var names only. Never print secrets.
