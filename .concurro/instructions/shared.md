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
