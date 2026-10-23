---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-plugin-sdk/blob/master/tools/constants/sections.mjs
---

# React

Hooks and runtime types for plugin UI written as React components. A component is handed to ONLYOFFICE Apps through one of the `*Component` props on an [item](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items.md), a [modal dialog](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IModalDialog.md) or the [settings block](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/settings/ISettings.md), and reads the portal selection, user, API and actions through these hooks.

Import from the `@onlyoffice/docspace-plugin-sdk/react` subpath, and keep `react` and both SDK entry points external in the plugin bundle — ONLYOFFICE Apps supplies its own copies, and a second React instance breaks every hook.

## Overview

The React API is split across these pages:

| Page | Description |
| --- | --- |
| [`PluginActions`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/actions.md) | Portal-side actions available to a React plugin component. |
| [`Api`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/api.md) | The portal API as a plugin sees it: the client every request goes through, the options a request takes, and the error a failure arrives as. |
| [`Hooks`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/hooks.md) | React hooks for plugin components rendered inside the ONLYOFFICE Apps application tree. |
| [`Runtime`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/runtime.md) | What ONLYOFFICE Apps hands a React plugin component: the current selection, the current user, and the clients the component reaches the portal with. |
| [`PluginSettingsClient`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/settings.md) | Client for persisting and retrieving plugin-specific settings. |