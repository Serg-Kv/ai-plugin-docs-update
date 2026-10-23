# SetPluginsOptions

Configures plugins from an external source.

The settings can be set for all plugins or for a specific plugin. For example, this method can be used to pass an authorization token to the plugin.

:::note
This method can be used only with the [connector class](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/usage-api/automation-api/connector-class.md).
:::

## Syntax

```javascript
expression.SetPluginsOptions(options);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| options | Required | [PluginOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/PluginOptions.md) |  | Plugin options. |

## Returns

This method doesn't return any data.
