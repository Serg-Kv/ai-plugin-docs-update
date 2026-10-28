---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-plugin-sdk/blob/master/tools/constants/sections.mjs
---

# Plugins

Core plugin interfaces that define the contract for each plugin type supported by ONLYOFFICE Apps. Every plugin must implement `IPlugin` plus one or more type-specific interfaces.

Implement the interface that matches the ONLYOFFICE Apps UI area you want to extend. Each plugin type registers its UI entries as [items](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items.md) kept in a `Map`.

## Overview

Available plugin type interfaces:

| Interface | Description |
| --- | --- |
| [`IApiPlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IApiPlugin.md) | The plugin that is provided with the origin, proxy, and prefix to make requests to the portal server. |
| [`IArticleButtonPlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IArticleButtonPlugin.md) | Describes a plugin that adds custom button items to the article sidebar. |
| [`IArticleNavigationPlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IArticleNavigationPlugin.md) | Describes a plugin that adds navigation items to the article sidebar. |
| [`IContextMenuPlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IContextMenuPlugin.md) | The plugin that is embedded in the context menu of files, folders, rooms, images, video (audio). |
| [`IEventListenerPlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IEventListenerPlugin.md) | The plugin that is given the access to the portal events. |
| [`IFilePlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IFilePlugin.md) | The plugin that can interact with the file list. |
| [`IInfoPanelPlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IInfoPanelPlugin.md) | The plugin that is embedded as a separate tab in the file info panel. |
| [`IMainButtonPlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IMainButtonPlugin.md) | The plugin that can add items to the main button menu. |
| [`IPlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IPlugin.md) | The default plugin, implemented by every plugin class together with the interfaces of the scopes it declares, such as [`IContextMenuPlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IContextMenuPlugin.md). |
| [`IPostMessagePlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IPostMessagePlugin.md) | The plugin that is given the access to handle postMessage events from iframe components. |
| [`IProfileMenuPlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IProfileMenuPlugin.md) | Plugin for embedding items in the profile menu. |
| [`ISettingsPlugin`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/ISettingsPlugin.md) | The plugin that manages settings for the administrator or owner. |