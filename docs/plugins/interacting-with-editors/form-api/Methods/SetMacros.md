# SetMacros

Sets macros to the document.

## Syntax

```javascript
expression.SetMacros(data);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| data | Required | [Macros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Enumeration/Macros.md) |  | The *Macros* object containing the data about all the macros from the document. |

## Returns

This method doesn't return any data.

## Example

```javascript
window.Asc.plugin.executeMethod ("SetMacros", [JSON.stringify (Content)], function () {
    window.Asc.plugin.executeCommand ("close", "");
});
```
