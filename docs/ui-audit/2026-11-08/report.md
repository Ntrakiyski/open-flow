# OpenFlow UI audit, 8 November 2026

Deployed and verified: https://openflow.159.69.35.245.sslip.io

Commit: [5418108](https://github.com/Ntrakiyski/open-flow/commit/5418108b29315872ff2d6201fdd97503b8aacd5a). The Coolify deployment finished; the running image has this commit and is healthy.

## What changed

The production compiler was converting `light-dark()` colors into fallback variables but could not generate the switches for a dynamic `color-scheme`. Light and dark color strings concatenated into invalid values, breaking backgrounds, borders and text throughout the app. Literal light/dark schemes fix the shared owner. A regression test exercises the production CSS transformation and failed before the repair.

Host navigation, card headings and action rows now wrap; long labels and errors remain inside cards. The variable editor scrolls when multiline values exceed the viewport. No product features, APIs, workflow logic, dependencies, credentials or provider settings were changed.

A proposed shared-dialog scrolling rule clipped nested tag menus. Browser review caught this; that rule was removed. Only the variable form, which has no nested portal menu, received a scroll constraint.

## Evidence

- Root `bun run check`: passed on the final committed source, including formatting, lint, locales and types.
- Product tests: 3,367 passed. Affected host suites: 54 passed. Variable suite also passed after its targeted scroll change.
- Final public-package consumer test: passed. Final production server build: passed.
- Desktop Chrome: login, empty/populated workflow lists, invalid names, creation, tag menus, node picker and empty search, code inspector, JSON values, title editing, undo/redo, local publication, successful code run/results and intentional failure/timeline/overview inspected.
- Host screens: settings, connector form, users/create user, variables and long multiline editing, CLI/MCP setup and event-source empty state inspected. Local narrow layouts checked at 320 and 390 CSS pixels; long forms at 351 × 360. No page overflow on the measured narrow host screens.

Live verification confirmed light/dark palette values and light persistence after reload, normal modal surfaces and complete tag menus, the two existing workflows and connected Gmail/Board/Google/OLX/YouTube catalog. No live workflow was edited, published or run.

After deployment and browser inspection, all rows in `flows`, `revisions`, `flow_revisions`, `flow_presentations`, `publications` and `flow_live` matched the predeployment SQLite backup. The private VPS backup passed SQLite quick_check.

## CLI and MCP control

Both interfaces were tested against the deployed VPS using its existing operator credential in process memory. CLI listed the two existing workflows. The official MCP client negotiated protocol `2026-07-28`, discovered 39 tools and returned the same workflows through `flow_list`. Authoring, validation, run and publish tools are advertised. Endpoint: `https://openflow.159.69.35.245.sslip.io/v1/mcp`.

These were read-only live checks. Actual editing, validation, running and publication were exercised only against disposable local audit data. No new personal token or persistent agent configuration was created.

## Limits

Paid model calls and actual external-provider actions were excluded. Browser file-import upload was blocked by the Chrome extension's disabled file-URL permission; malformed JSON was rejected by the CLI as the next-best boundary check. The package's optional Node PNG renderer was not run because no prepared Chromium executable was configured; real Chrome screenshots supplied visual UI evidence. This audit covers the recorded paths, not every possible workflow or provider combination.

Local audit servers were stopped and their disposable database/token removed. The user's earlier local OpenFlow installation and unrelated apps were preserved.

## Screenshots

### Before and deployed result

[before flows dark](./before-flows-dark.jpg)

[before create dialog](./before-create-dialog.jpg)

[after live flows dark final](./after-live-flows-dark-final.jpg)

[after live flows light](./after-live-flows-light.jpg)

[after live settings dark](./after-live-settings-dark.jpg)

[after live create tags light](./after-live-create-tags-light.jpg)

### Editor and execution

[local production inspector dark](./local-production-inspector-dark.jpg)

[local production run success dark](./local-production-run-success-dark.jpg)

[local production run success light](./local-production-run-success-light.jpg)

[local run failure dark](./local-run-failure-dark.jpg)

[local execution overview dark](./local-execution-overview-dark.jpg)

[after live provider picker dark](./after-live-provider-picker-dark.jpg)

[after live gmail actions dark](./after-live-gmail-actions-dark.jpg)

### Edge cases and host screens

[local invalid flow name](./local-invalid-flow-name.jpg)

[local tags short height](./local-tags-short-height.jpg)

[local variable long short height](./local-variable-long-short-height.jpg)

[local agents 320 dark](./local-agents-320-dark.jpg)

[local mcp 320 dark](./local-mcp-320-dark.jpg)

[local settings 390 light](./local-settings-390-light.jpg)

[local event sources empty dark](./local-event-sources-empty-dark.jpg)

[local picker no results light](./local-picker-no-results-light.jpg)

[local production login light](./local-production-login-light.jpg)
