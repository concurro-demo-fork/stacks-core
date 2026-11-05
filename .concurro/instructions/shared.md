# Demo target

The operator explicitly permits AI-assisted contributions to
`concurro-demo-upstream/stacks-core`, using `concurro-demo-fork/stacks-core` for work.
Do not open issues or PRs in `stacks-network/stacks-core`.

Use the repository's engineering conventions. For this demonstration, the CI and
contribution flow in `docs/concurro-demo.md` replace the production workflow described
in CONTRIBUTING.md. Do not require the production CI matrix or its internal review
process. The controller handles publication, independent review and readiness; agents
do not push branches, publish PRs or merge.

Demo CI builds and tests only stacks-common and checks its formatting. Use focused
tests appropriate to the requested change, and distinguish those results from coverage
of other crates. Never describe the limited demo checks as full production validation.
