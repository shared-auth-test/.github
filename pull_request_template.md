## Acceptance surface

- [ ] Source repositories and actions are pinned to immutable commits.
- [ ] Declared Git submodule, Zed, and native-package lanes are preserved.
- [ ] Product assertions execute; this is not a no-op or metadata-only success.
- [ ] Failure and recovery paths execute where applicable.
- [ ] Failure classification is explicit: product regression, blocked dependency, or harness regression.
- [ ] Gated integration has a real executable entrypoint and fails closed without it.
- [ ] Fixtures are synthetic; logs and artifacts contain no credentials, biometrics, production data, private messages, or recordings.
- [ ] Overlapping or superseded work has a semantic trace for every unique invariant retained or intentionally rejected.

## Salvage check

If this PR supersedes or replaces an older one, say which, and name at least one
concrete thing carried forward from it (a test, a fixture, an error message, a
pin, a doc paragraph). See [`docs/pr-salvage-policy.md`](../docs/pr-salvage-policy.md).

- [ ] Supersedes nothing, **or** the salvaged item is named above.
