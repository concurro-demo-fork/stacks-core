# Implementation

Use the pinned repository toolchain. For stacks-common work, run:

```bash
cargo fmt -p stacks-common -- --check
cargo nextest run --locked -p stacks-common --lib --test-threads 4
```

Use focused tests or checks for other touched code when needed; do not invoke the full
upstream CI matrix. Report exactly what ran, failures and anything you could not finish.
Generate lockfiles with Cargo rather than editing dependency checksums by hand.
Follow changelog.d/README.md when the requested change needs a changelog fragment.
