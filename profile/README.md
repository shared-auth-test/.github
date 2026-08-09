# shared-auth-test

Independent acceptance organization for **shared-auth**.

The authenticated live inventory contains 23 test repositories: 19 generated specialized harnesses and 4 legacy independent harnesses.

## Generated specialized fleet

| Repository | Surface |
|---|---|
Private repository details are intentionally withheld from this public document.

Each repository’s `test-plan.json` is authoritative. Metadata validation is not live integration. Gated integration must have an executable entrypoint and fail closed until its dependencies are available.

## Preserved legacy fleet

| Repository | Unique coverage retained pending semantic comparison |
|---|---|
Private repository details are intentionally withheld from this public document.

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


<!-- ore-org-baseline:begin -->
## Planning and governance

- Canonical Linear project: https://linear.app/denman/project/githubcomshared-auth-test-b01af6233a25
- Organization defaults: https://github.com/shared-auth-test/.github
- Canonical agent policy: https://github.com/shared-auth-test/.github/blob/main/agents.md
- Security policy: https://github.com/shared-auth-test/.github/security/policy

Repositories in this organization use semantic conflict resolution with 3–10 relevant prior commits when useful, full cross-repository context, pull-request delivery, and a hard automated-agent denylist for destructive or history-rewriting operations.
<!-- ore-org-baseline:end -->

<!-- BEGIN MANAGED REPOSITORY RELATIONSHIPS v1 -->
## Repository relationship registry

`shared-auth-test` declares repository roles, dependency edges, cross-organization capabilities, deployment ownership, and the git-submodule/Zed-package contract:

- [Human-readable map](architecture/REPOSITORY_RELATIONSHIPS.md)
- [Machine-readable manifest](architecture/repository-relationships.json)
- [JSON Schema](architecture/repository-relationships.schema.json)

The public registry withholds private repository names and edges.
<!-- END MANAGED REPOSITORY RELATIONSHIPS v1 -->
