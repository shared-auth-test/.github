# Shared Auth test-fleet reconciliation

Audit date: 2026-08-05

The canonical portfolio declares one policy repository plus ten identity, protocol, recovery, verification, bridge, abuse, and UI repositories for `shared-auth-test`. Five repositories currently exist.

## Present

- `.github`
- `lib-clients-consumer-matrix`
- `oidc-oauth-contract`
- `passwordless-passkeys`
- `session-revocation`

## Missing canonical certification repositories

- `account-recovery-govid`
- `face-verification`
- `voice-verification-voxletra`
- `nats-bridge-replay`
- `abuse-rate-limits`
- `ui-mcp-e2e`

## Hardening already in progress

`shared-auth-test/session-revocation#1` adds executable device/session revocation, refresh-token family replay, refresh-versus-revoke race, WebSocket invalidation, auditability, and fail-closed dependency contracts.

## Completion rule

The organization is not considered fully certified until all six missing repositories are provisioned with synthetic fixtures, immutable source coordinates, credential-free pull-request checks, and explicit separation of product, dependency, and harness failures.
