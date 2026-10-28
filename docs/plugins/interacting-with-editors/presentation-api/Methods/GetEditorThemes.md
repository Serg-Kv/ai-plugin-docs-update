# GetEditorThemes

Returns the list of available editor themes.

:::note
This functionality is available in paid ONLYOFFICE Docs editions.
:::

## Syntax

```javascript
expression.GetEditorThemes();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

object[]

## Example

```javascript
window.Asc.plugin.executeMethod("GetEditorThemes", null, function(themes) {
	console.log(themes);
});
```
