# shared-auth-test

Independent acceptance organization for **shared-auth**.

The authenticated live inventory contains 23 test repositories: 19 generated specialized harnesses and 4 legacy independent harnesses.

## Generated specialized fleet

| Repository | Surface |
|---|---|
| `server-api-contract-e2e` | Users, sessions, factors, tokens, tenants, errors, limits |
| `oidc-provider-e2e` | Discovery, authorization code, nonce/state, JWKS, logout |
| `oauth-pkce-e2e` | S256 PKCE, exact redirects, state, replay, token exchange |
| `webauthn-passkey-e2e` | Platform/roaming authenticators, resident keys, counters, origins |
| `totp-recovery-e2e` | TOTP skew, backup codes, single use, cooldown, audit |
| `biometric-recovery-policy-e2e` | ID, face, voice, consent, review, minimization policy |
| `session-rotation-e2e` | Login/privilege rotation, logout-all, devices, concurrency |
| `refresh-token-reuse-e2e` | Rotation, reuse detection, family revoke, races, audit |
| `jwks-key-rotation-e2e` | Overlap windows, old/new validation, caches, rollback |
| `tenant-isolation-e2e` | User/client isolation, scopes, RLS, audit |
| `clients-rust-consumer` | Rust SDK and OAuth flow consumption |
| `clients-typescript-consumer` | Browser/Node TypeScript SDK and PKCE |
| `clients-dart-consumer` | Dart/Flutter SDK, secure storage, PKCE |
| `clients-go-consumer` | Go SDK, service authentication, contexts |
| `sync-offline-e2e` | Offline session/factor state, restart, revocation precedence |
| `nats-dlq-e2e` | Events, redelivery, DLQ, poison messages, ordering |
| `audit-log-redaction-e2e` | Secret/biometric redaction, correlation, tamper evidence |
| `three-browser-e2e` | Playwright/Puppeteer/Selenium auth and accessibility |
| `mcp-contract-e2e` | Read/admin tools, authorization, redaction, schemas |

Each repository’s `test-plan.json` is authoritative. Metadata validation is not live integration. Gated integration must have an executable entrypoint and fail closed until its dependencies are available.

## Preserved legacy fleet

| Repository | Unique coverage retained pending semantic comparison |
|---|---|
| `lib-clients-consumer-matrix` | Cross-library/client consumer matrix |
| `oidc-oauth-contract` | Independent OAuth/OIDC protocol fixtures |
| `passwordless-passkeys` | Independent passwordless/passkey scenarios |
| `session-revocation` | Session revocation and refresh-race contracts |

These repositories are not retirement candidates merely because generated names overlap. Retirement requires evidence that all unique behavior and relevant history have been preserved.

Names previously documented as repositories but absent from the authenticated installation inventory are omitted rather than represented as live coverage.

Pull-request checks remain deterministic and credential-free. Private cross-organization materialization requires approved short-lived GitHub App installation tokens, with no PAT or persistent-token fallback.

<!-- org-project-routing:start -->
## Planning and delivery

- [GitHub Project: shared-auth-test-project](https://github.com/orgs/shared-auth-test/projects/1)
- [Linear planning project](https://linear.app/denman/project/githubcomshared-auth-test-b01af6233a25)
- [Detailed project-routing contract](../docs/PROJECTS.md)

GitHub owns code and delivery evidence; Linear owns planning and dependencies. The linked organization Project provides the cross-repository execution view.
<!-- org-project-routing:end -->
