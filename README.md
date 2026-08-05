# shared-auth-test governance

Organization-wide community health, privacy, and reusable workflow policy for Shared Auth acceptance testing.

The authenticated live inventory contains **23 test repositories** plus this governance repository:

- **19 generated specialized harnesses** for API, OAuth/OIDC, WebAuthn, recovery, session rotation, token reuse, JWKS, tenant isolation, SDKs, offline sync, NATS/DLQ, audit redaction, browsers, and MCP.
- **4 legacy independent harnesses**: `lib-clients-consumer-matrix`, `oidc-oauth-contract`, `passwordless-passkeys`, and `session-revocation`.

The four legacy repositories remain first-class until a semantic behavior/history comparison proves that every unique invariant has an explicit destination. Names previously documented but absent from the authenticated repository inventory are not represented as live repositories.

## Policy

- Pin source repositories and actions to immutable commits.
- Preserve declared Git submodule, Zed, and native-package dependency lanes.
- Run deterministic, credential-free checks on pull requests.
- Classify failures as product regressions, blocked dependencies, or harness regressions.
- Never report metadata validation as live integration success.
- Require a real executable integration entrypoint before gated integration may pass.
- Use approved short-lived GitHub App installation tokens for private cross-organization materialization; do not add PAT or persistent-token fallbacks.
- Use synthetic fixtures and keep credentials, production data, biometrics, private messages, and recordings out of logs and artifacts.
