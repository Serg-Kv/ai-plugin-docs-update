# SetEditingRestrictions

Sets the document editing restrictions.

## Syntax

```javascript
expression.SetEditingRestrictions(restrictions);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| restrictions | Required | [DocumentEditingRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/DocumentEditingRestrictions.md) |  | The document editing restrictions. |

## Returns

This method doesn't return any data.

## Example

```javascript
window.Asc.plugin.executeMethod("SetEditingRestrictions", ["readOnly"]);
```
