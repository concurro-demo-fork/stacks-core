# Demo target

The operator explicitly permits AI-assisted contributions to
`concurro-demo-upstream/stacks-core`, using `concurro-demo-fork/stacks-core` for work.
Do not open issues or PRs in `stacks-network/stacks-core`.

Follow CONTRIBUTING.md's engineering conventions. The operator's AI permission above
applies only to these demo repositories. For this demonstration, the configured demo
CI and Concurro's contribution flow replace the production CI matrix and internal
review process. The controller handles publication, independent review and readiness;
agents do not push branches, publish PRs or merge.

Use the demo CI workflow and its shared build action in the checked-out revision as
the source of truth for tested packages, features and filters. Run focused tests
appropriate to the requested change, and distinguish those results from CI coverage.
Never describe the limited demo checks as full production validation.

# Code search

The `lodestone` MCP server indexes the definitions in your checkout, including your edits.
Its tools find code by what it does, which a text search cannot when you do not know the name.

| Situation | Tool | Input |
| ---- | ---- | ---- |
| Before writing a helper, type, trait or macro | `semantic_code_search` | what it must do |
| Locating described behaviour | `semantic_code_search` | the behaviour |
| Reviewing or refactoring | `similar_code_search`, once | each added or moved function, one per entry |

- `semantic_code_search` takes `query`, one plain sentence, and `example_identifiers`, three
  to five guessed names in this codebase's style. Wrong guesses still help. Rephrase around
  the capability and search again when the answer is missing.
- Results are `path:line:col  lines start-end  kind name(signature) — doc`. Read the likely
  candidates, and reuse what fits instead of writing another version.
- Use a text search for exact strings: an error message, a known identifier, a config key.
- When the tools are missing, fail or report a stale index, continue with the shell and the
  source. Empty results do not show that no such code exists.
