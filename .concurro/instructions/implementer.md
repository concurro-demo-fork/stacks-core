# Implementation

Use the pinned repository toolchain. Select packages, features and focused tests for
the changed behavior and affected callers. Inspect the checked-out demo workflow and
shared build action for CI coverage; do not assume that one crate covers the change.
Use `cargo nextest run --locked` for tests and `cargo fmt -p <package> -- --check` for
each affected package. Include relevant feature flags, such as SQLite support when
testing SQLite behavior.

Do not invoke the full upstream CI matrix. Report exactly what ran, failures and
anything you could not finish; distinguish local checks from CI results.
Generate lockfiles with Cargo rather than editing dependency checksums by hand.
Follow changelog.d/README.md when the requested change needs a changelog fragment.
