# Agent patterns and collections

A pattern is a repeatable workflow. A central control repo that dispatches workers is one pattern. The control repo chooses the job and the target. Each worker opens a pull request for its own edit. Workers do not push the default branch.

A collection is a named bundle of agents, instructions, and prompts for one job. The file is `assets/collections/<id>.collection.yml`. Each item has a `path` under `assets/` and a `kind` such as `agent`, `instruction`, or `prompt`.

Three collections cover the jobs in this set. `coding-standards` holds the strategy interview, git init, Cursor rules, code review, and Clerk auth standards. `compound-delivery` holds compound notes, problem PRs, spec-to-implementation, orchestration, CLIs for agents, and Clerk setup. `harness-ops` holds PenguinHarness work, stacked PR landing, simplifications, prose, archival, caveman mode, and the control-repo instruction.

Relevance comes from the job, the files in scope, and whether the agent owns a decision the others do not. A review agent owns the report. A setup agent owns the first install. Do not add an agent because the name sounds related.

To add one, write `assets/agents/<name>.agent.md` with `description`, `name`, `model`, and `tools` in the frontmatter. Add a collection item whose path exists on disk. Run `node scripts/analysis/validate-assets.js`. Then run `npm run generate-manifest` so `assets-manifest.json` lists the new files.

Continual learning lives in PenguinHarness, not in this catalog. The stop hook in `plugins/continual-learning/hooks/stop.mjs` fires only after a Task exceeds 30 completed turns. It condenses that Task and asks a background subagent to fold durable findings into the agent's own skills. A short Task emits nothing.
