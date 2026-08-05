# Contributing

Keep tests black-box where possible and use synthetic data. Classify every failure as a product regression, blocked dependency, or harness regression.

Preserve immutable source pins and every declared Git submodule, Zed, or native-package dependency lane. Add product assertions rather than replacing contract checks with no-op smoke tests. A gated integration workflow must fail closed unless it executes a real product entrypoint.

Pull-request checks must be deterministic and credential-free. Put live providers, emulators, databases, chaos, scale, and soak checks in scheduled or manually gated workflows.

When branches or repositories overlap, reconcile behavior and recent history. Do not mechanically select one side, and do not retire a repository until every unique invariant and relevant history has an explicit destination.
