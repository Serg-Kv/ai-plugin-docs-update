---
sidebar_position: -1
---

# Overview

The plugins and macros can interact with the editors using the [Asc.plugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/asc-plugin.md) object — its [events](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/asc-plugin.md#events), methods, and commands. Here you will find how to use them.

- [Asc.plugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/asc-plugin.md) — the main plugin object: properties, methods, and events
- [How to attach events](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/how-to-attach-events.md) — listening for editor events
- [How to call methods](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/how-to-call-methods.md)
- [How to call commands](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/how-to-call-commands.md)

The main plugin code is placed to a *.js* file which describes what and how must be done by the plugin. This file is placed to the plugin root folder together with the [config.json](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/configuration.md) and [index.html](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/configuration/entry-point.md) files.

## How it works

Any plugin has the [Asc.plugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/asc-plugin.md) object which provides methods and events to interact with ONLYOFFICE document, spreadsheet, presentation, and PDF editors.

:::note
Starting from version 7.1, the access to the *window* and *document* objects and the *alert* function is restricted from the plugin command code because the *"use strict"* mode was applied to the plugin scripts. Don't forget to declare variables before using them so that the plugins work correctly.
:::

For the plugin to work the developer must specify two obligatory events for the `Asc.plugin` object: [init](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/asc-plugin.md#init) and [button](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/asc-plugin.md#button). After that:

- [Editor.RunMacro](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/how-to-call-commands.md#editorrunmacro) is used to execute multiple [Office JavaScript API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/get-started/overview.md) commands in a single call.
- The [Editor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/how-to-call-methods.md#editor-object) object is used to run a single editor method (e.g. `await Editor.AddComment(...)`, `await Editor.GetSelectedText(...)`).

Both return a Promise. In editors before version 10.0, use [callCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/how-to-call-commands.md#callcommand) and [executeMethod](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/how-to-call-methods.md#executemethod) instead.

If the plugin operates with an OLE object, [callCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/how-to-call-commands.md#callcommand) is used to manage it.

See the [Asc.plugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/asc-plugin.md#minimal-example) page for a minimal working example, or the [Getting started](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/get-started/overview.md) guide for a full walkthrough. More open source plugin examples can be found [here](https://api.onlyoffice.com/samples/?doctype=docs&text=plugin).
