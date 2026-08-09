# Cross-organization source access

Tracking: Linear `DEN-2918`; GitHub `shared-auth-test/.github#10`.
Qualification PR: `shared-auth-test/clients-rust-consumer#3`.

## Policy

The shared-auth test fleet reads private source through short-lived installation
tokens from a dedicated, selected-repository GitHub App. Deploy keys and broad
reusable personal access tokens are prohibited as the permanent source-checkout
mechanism.

The App should receive Contents and Metadata read only. Administration, Actions
secrets, deploy keys, workflow write, branch write, release write, package write,
and unrelated-repository access are denied unless a separate reviewed workflow
requires them.

## Organization configuration

Selected test repositories that use `actions/create-github-app-token` expect:

```text
CROSS_ORG_APP_ID
CROSS_ORG_APP_PRIVATE_KEY
```

The App ID is an organization variable. The private key is an encrypted
organization secret restricted to selected repositories. Neither value belongs
in source, generated files, logs, caches, artifacts, issue text, or Linear.

The generated installation token must be short-lived, repository-scoped, and
used only for checkout. Every checkout pins a 40-character source SHA and sets
`persist-credentials: false`.

## Fail-closed behavior

Missing variables, unavailable secrets, failed token creation, or checkout denial
is an infrastructure-blocked result. It is not a source-test failure and must not
be described as one.

After a credential-stage failure:

- compiler, database, format, Clippy, test, package, and release steps remain
  skipped;
- the pull request stays draft or clearly marked blocked;
- no deploy key or broad PAT is introduced as an emergency workaround;
- the configuration issue is linked from the PR and Linear;
- the source heads are refreshed before rerunning after a prolonged block.

`shared-auth-test/clients-rust-consumer#3` is the current example: both jobs
started, but token creation failed before checkout. Remediation is tracked in
`shared-auth-test/.github#10` and Linear `DEN-2918`.

## Credential canary

Before enabling source qualification, a canary must prove:

1. approved private shared-auth source checkout succeeds at an immutable SHA;
2. an unapproved repository checkout fails;
3. branch/tag creation fails;
4. workflow, release, package, secret, and deploy-key writes fail;
5. secret and deploy-key enumeration fail;
6. the token is absent from `.git/config`, logs, artifacts, caches, and generated
   files after checkout cleanup;
7. installation revocation makes the next run fail closed.

Canary evidence belongs on `shared-auth-test/.github#10` and is linked from Linear
`DEN-2918`.

## Qualification contract

Once credential provisioning is green, shared-auth qualification should pin the
current merged or released source revisions and execute:

- server PostgreSQL schema application and Redis-backed revocation context;
- Rust formatting and Clippy with warnings denied;
- all-target tests and release build;
- client workspace formatting, Clippy, native tests, and metadata checks;
- delegated issuer/audience/client/session/scope/current-parent lineage tests;
- credential-isolation and redirect/body-bound tests.

A historical red run against obsolete source SHAs is not current evidence. Update
exact source revisions before rerunning a previously blocked PR.

## Credential-outage fallback

A content-addressed source snapshot may preserve bounded validation while App
configuration is unavailable. Its manifest must record upstream repository,
immutable commit, and Git blob ID for every file; CI recomputes those Git blob
IDs before execution.

Snapshot evidence proves only the recorded source bytes. It does not prove that
live private checkout or GitHub App selection is configured. Keep those controls
separate in the GitHub Project.

## Rotation and incident response

Record App installation IDs, selected repositories, owner, creation date,
rotation deadline, and revocation procedure in the approved secret-management
system. Rotate the App private key under two-person review where available.

On suspected exposure, revoke first, remove obsolete encrypted secrets and refs,
scan source/history without printing secret bytes, qualify replacement access in
a `*-test` repository, and preserve only non-secret identifiers and timestamps.

## GitHub Project fields

Track access work in project 1 with:

- **Linear:** `DEN-2918` or the specific dependent issue;
- **Control:** App installation / selected repository / canary / rotation / incident;
- **Source revision:** immutable commit or release;
- **Credential class:** GitHub App / temporary fine-grained token / snapshot fallback;
- **Status:** blocked / configured / canary green / qualified / rotated / revoked;
- **Evidence:** exact workflow run or administrator record;
- **Expiry or next rotation:** absolute date;
- **Blocked by:** issue or administrator action.
