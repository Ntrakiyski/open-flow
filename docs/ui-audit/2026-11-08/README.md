# OpenFlow UI audit screenshots

26 captures from the 8 November 2026 audit, covering the deployed UI, before/after states and disposable local tests. Local workflow data is sample data.

[Audit report, validation and limitations](./report.md) · [UI fix commit](https://github.com/Ntrakiyski/open-flow/commit/5418108b29315872ff2d6201fdd97503b8aacd5a)

The deployed UI now renders both themes correctly. Browse each group below; select an image to open the original capture.

<details>
<summary>Deployed interface (7)</summary>

### Deployed workflow list in dark mode

![Deployed workflow list in dark mode](./after-live-flows-dark-final.jpg)

### Deployed workflow list in light mode

![Deployed workflow list in light mode](./after-live-flows-light.jpg)

### Deployed service settings in dark mode

![Deployed service settings in dark mode](./after-live-settings-dark.jpg)

### New Flow dialog with its complete tag menu

![New Flow dialog with its complete tag menu](./after-live-create-tags-light.jpg)

### Connected providers in the node picker

![Connected providers in the node picker](./after-live-provider-picker-dark.jpg)

### Gmail trigger and action catalog

![Gmail trigger and action catalog](./after-live-gmail-actions-dark.jpg)

### Deployed dark list, initial verification capture

![Deployed dark list, initial verification capture](./after-live-flows-dark.jpg)

</details>

<details>
<summary>Before the fixes (3)</summary>

### Before: dark mode selected but colors rendered light

![Before: dark mode selected but colors rendered light](./before-flows-dark.jpg)

### Before: invalid palette left the dialog surface transparent

![Before: invalid palette left the dialog surface transparent](./before-create-dialog.jpg)

### Before: agent access screen with broken dark colors

![Before: agent access screen with broken dark colors](./before-agents-dark.jpg)

</details>

<details>
<summary>Local editor and execution checks (7)</summary>

### Code inspector with sample customer data

![Code inspector with sample customer data](./local-production-inspector-dark.jpg)

### Successful local run in dark mode

![Successful local run in dark mode](./local-production-run-success-dark.jpg)

### Successful local run in light mode

![Successful local run in light mode](./local-production-run-success-light.jpg)

### Intentional local failure and timeline

![Intentional local failure and timeline](./local-run-failure-dark.jpg)

### Execution overview with readable error details

![Execution overview with readable error details](./local-execution-overview-dark.jpg)

### Local publication in progress

![Local publication in progress](./local-publish-dark.jpg)

### Local production build with a long workflow name

![Local production build with a long workflow name](./local-production-flows-dark.jpg)

</details>

<details>
<summary>Responsive layouts and edge cases (7)</summary>

### Invalid workflow name validation

![Invalid workflow name validation](./local-invalid-flow-name.jpg)

### Tag menu at a short viewport height

![Tag menu at a short viewport height](./local-tags-short-height.jpg)

### Long multiline variable in a scrolling dialog

![Long multiline variable in a scrolling dialog](./local-variable-long-short-height.jpg)

### CLI setup at 320 CSS pixels

![CLI setup at 320 CSS pixels](./local-agents-320-dark.jpg)

### MCP setup at 320 CSS pixels

![MCP setup at 320 CSS pixels](./local-mcp-320-dark.jpg)

### Service settings at 390 CSS pixels

![Service settings at 390 CSS pixels](./local-settings-390-light.jpg)

### Node picker search with no matching query

![Node picker search with no matching query](./local-picker-no-results-light.jpg)

</details>

<details>
<summary>Empty and authentication screens (2)</summary>

### Empty sign-in form in the production build

![Empty sign-in form in the production build](./local-production-login-light.jpg)

### Event-source empty state

![Event-source empty state](./local-event-sources-empty-dark.jpg)

</details>
