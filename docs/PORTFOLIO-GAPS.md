# Shared Auth test-fleet reconciliation

Audit date: 2026-08-05
Canonical source: `zed-pkg-test/zed-pkg-e2e` live 341-repository manifest

## Current result

The live portfolio declares **19 specialized repositories plus one public `.github` governance repository** for `shared-auth-test`: **20 canonical repositories** in total.

The remote organization currently contains **5 repositories**, leaving a **count gap of 15**. The present repositories are:

- `.github`
- `lib-clients-consumer-matrix`
- `oidc-oauth-contract`
- `passwordless-passkeys`
- `session-revocation`

The previous six-repository gap list came from an older fleet snapshot and is superseded by the live manifest. The exact missing name set must be generated from the deterministic canonical index proposed in `zed-pkg-test/zed-pkg-e2e#94`; it must not be guessed from stale exports.

## Required coverage

The completed fleet must cover OAuth/OIDC/WebAuthn, tenant isolation, clients, sessions and revocation, account recovery, identity verification, NATS/DLQ replay, abuse controls, synchronization, auditing, and UI/MCP integration with synthetic identities and media only.

## Hardening in progress

`shared-auth-test/session-revocation#1` adds executable device/session revocation, refresh-token family replay, refresh-versus-revoke race, WebSocket invalidation, auditability, and fail-closed dependency contracts.

## Completion rule

The organization is not fully certified until all 20 canonical repositories are present by exact name, generated bootstrap pull requests are merged in dependency order, and fixtures remain free of government IDs, biometrics, recordings, tokens, and signing keys. Extra repositories remain intact.
