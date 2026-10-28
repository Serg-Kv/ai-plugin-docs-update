---
sidebar_position: -4
---

# Coding plugin

Develop a plugin. Follow the plugin structure described [here](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/plugin-structure.md).

- Write code for each [plugin type](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins.md) using the corresponding variables, methods and [items](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items.md). Put the scripts into the *src* folder. Specify the required [Plugin](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IPlugin.md) interface for each plugin to be embedded in the portal:

  - [API](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IApiPlugin.md)
  - [article button](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IArticleButtonPlugin.md)
  - [article navigation](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IArticleNavigationPlugin.md)
  - [context menu](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IContextMenuPlugin.md)
  - [event listener](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IEventListenerPlugin.md)
  - [file](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IFilePlugin.md)
  - [info panel](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IInfoPanelPlugin.md)
  - [main button](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IMainButtonPlugin.md)
  - [postMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IPostMessagePlugin.md)
  - [profile menu](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IProfileMenuPlugin.md)
  - [settings](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/ISettingsPlugin.md)

  ![Plugin structure](https://api.onlyoffice.com/assets/images/docspace/plugin-structure.png#gh-light-mode-only)![Plugin structure](https://api.onlyoffice.com/assets/images/docspace/plugin-structure.dark.png#gh-dark-mode-only)

- Specify [plugin messages](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/utils.md) that will be returned by the items. Use the appropriate [events](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/enums/Actions.md) that will be processed on the portal side.

- Learn which [plugin components](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components.md) can be used for the ONLYOFFICE Apps plugin interface and add them to your scripts. You can also pass a React component through the `component` or `dialogBodyComponent` property instead of a declarative [IBox](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IBox.md) tree.

## React components

An item can render a React component instead of a declarative [IBox](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IBox.md) tree. Pass the component through:

- `component` on [IInfoPanelItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IInfoPanelItem.md), [IArticleButtonItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IArticleButtonItem.md), [IArticleNavigationItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IArticleNavigationItem.md), [IMediaViewer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IMediaViewer.md), and [ISettings](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/settings/ISettings.md)
- `dialogBodyComponent` on [IModalDialog](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IModalDialog.md)

The component is rendered inside the ONLYOFFICE Apps application tree and reaches the portal through the hooks from *@onlyoffice/docspace-plugin-sdk/react*:

``` tsx
import {
  usePluginAPI,
  usePluginActions,
  usePluginSettings,
  useCurrentFile,
  useCurrentUser,
  usePluginRuntime,
} from "@onlyoffice/docspace-plugin-sdk/react";
```

### React API Reference

For complete React hooks and API documentation, see:

- **[React Hooks](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/hooks.md)** - `usePluginRuntime`, `useCurrentFile`, `usePluginActions`, `usePluginAPI`, `useCurrentUser`, `usePluginSettings`
- **[Plugin API Client](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/api.md)** - HTTP client methods, options, and error handling
- **[Plugin Actions](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/actions.md)** - Portal UI actions (toasts, modals, navigation)
- **[Plugin Runtime](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/runtime.md)** - Runtime context types
- **[Plugin Settings](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/settings.md)** - Settings management API

### Quick Example

```tsx
import { useEffect, useState } from "react";
import { usePluginAPI } from "@onlyoffice/docspace-plugin-sdk/react";

type MyDocuments = { files: { id: number; title: string }[] };

function FileList() {
  const api = usePluginAPI();
  const [files, setFiles] = useState<MyDocuments["files"]>([]);

  useEffect(() => {
    const controller = new AbortController();
    api
      .get<MyDocuments>("/files/@my", { count: 20 }, { signal: controller.signal })
      .then((folder) => setFiles(folder.files));
    return () => controller.abort();
  }, []);

  return <ul>{files.map((f) => <li key={f.id}>{f.title}</li>)}</ul>;
}
```

### External Dependencies

`react`, `react-dom`, `react/jsx-runtime`, *@onlyoffice/docspace-plugin-sdk/react*, and *@onlyoffice/apps-ui-kit* must stay out of the plugin bundle — ONLYOFFICE Apps supplies them at load time.

**Import only from `@onlyoffice/apps-ui-kit`; do not use subpath imports.** The portal only substitutes the exact package specifier `@onlyoffice/apps-ui-kit`. A plugin that imports `@onlyoffice/apps-ui-kit/components/button` will fail to load with an error: "…which the portal does not provide."

```tsx
// ✅ Correct
import { Button, Text } from "@onlyoffice/apps-ui-kit";

// ❌ Wrong — the portal cannot load this
import { Button } from "@onlyoffice/apps-ui-kit/components/button";
```

For the build configuration, see [building a plugin](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/building-plugin.md).

Code samples are available at [GitHub](https://github.com/ONLYOFFICE/docspace-plugins).
