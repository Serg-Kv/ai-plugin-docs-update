---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-plugin-sdk/blob/master/tools/constants/sections.mjs
---

# Items

Plugin items that extend specific ONLYOFFICE Apps UI locations — context menus, file rows, info panels, profile menus, and navigation buttons.

Choose the item interface that matches the ONLYOFFICE Apps UI area you want to extend with your plugin action. Items are registered through the matching [plugin type interface](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins.md). For example, a context menu plugin stores its `IContextMenuItem` objects in a `Map` and returns them from the `getContextMenuItems()` method.

## Overview

Each plugin type has specific items described in this section:

| Interface | Description |
| --- | --- |
| [`IArticleButtonItem`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IArticleButtonItem.md) | Describes a button item that will be embedded in the article sidebar. |
| [`IArticleNavigationItem`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IArticleNavigationItem.md) | Describes a navigation item that will be embedded in the article sidebar as a first-class navigation entry. |
| [`IContextMenuItem`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IContextMenuItem.md) | Describes an item that will be embedded in the context menu. |
| [`IEventListenerItem`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IEventListenerItem.md) | Describes an event listener that reacts to portal events. |
| [`IFileItem`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IFileItem.md) | Describes an item that will be embedded in the file list. |
| [`IInfoPanelItem`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IInfoPanelItem.md) | The info panel item that is displayed in the info panel. |
| [`IMainButtonItem`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IMainButtonItem.md) | Describes an item that will be embedded in the **More** submenu of the main button menu, which opens from the **New** button. |
| [`IProfileMenuItem`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IProfileMenuItem.md) | Describes an item that will be embedded in the profile menu. |