# shared-auth-test

Independent acceptance organization for **shared-auth**.

Library/clients, OAuth/OIDC, passkeys, sessions, recovery, biometrics, Voxletra, NATS, abuse limits, UI, and MCP certification.

## Portfolio

| Repository | Class | Readiness | Primary dependency path |
|---|---|---|---|
| `lib-clients-consumer-matrix` | SDK consumer | `ready` | `matrix` |
| `oidc-oauth-contract` | authentication | `ready` | `matrix` |
| `passwordless-passkeys` | authentication | `ready` | `matrix` |
| `session-revocation` | security | `ready` | `matrix` |
| `account-recovery-govid` | security | `ready` | `matrix` |
| `face-verification` | security | `ready` | `matrix` |
| `voice-verification-voxletra` | interoperability | `mixed` | `matrix` |
| `nats-bridge-replay` | interoperability | `ready` | `matrix` |
| `abuse-rate-limits` | security | `ready` | `matrix` |
| `ui-mcp-e2e` | UI/accessibility | `ready` | `matrix` |

Pull requests run deterministic harness checks. Emulators, desktop matrices, live APIs/providers, databases, chaos, scale, and soaks are scheduled/manual. Missing upstreams or credentials are blocked readiness—not false passes or product regressions.
