# SetDisplayModeInReview

Sets the display mode for track changes.

## Syntax

```javascript
expression.SetDisplayModeInReview(sMode);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| sMode | Optional | string | "edit" | The display mode: **edit** - all changes are displayed, **simple** - all changes are displayed but the balloons are turned off, **final** - all accepted changes are displayed, **original** - all rejected changes are displayed. |

## Returns

This method doesn't return any data.

## Example

```javascript
window.Asc.plugin.executeMethod ("SetDisplayModeInReview", ["edit"]);
```
