# GetRestrictions

Returns the restrictions the editor currently applies to the document.

## Syntax

```javascript
expression.GetRestrictions();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[EditorRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Enumeration/EditorRestrictions.md)

## Example

```javascript
window.Asc.plugin.executeMethod("GetRestrictions", [], function(restrictions) {
	if (restrictions & 0x80)
		console.log("The presentation cannot be changed");
});
```
