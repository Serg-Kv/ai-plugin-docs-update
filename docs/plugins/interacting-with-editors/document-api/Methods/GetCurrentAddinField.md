# GetCurrentAddinField

Returns the current addin field from the document.

## Syntax

```javascript
expression.GetCurrentAddinField();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[AddinFieldData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/AddinFieldData.md) \| null \| undefined

## Example

```javascript
window.Asc.plugin.executeMethod("GetCurrentAddinField", [], function(data){
	if (null === data) {
		console.log("No addin field at the current cursor position");
	} else {
		console.log("Current addin field:", data);
	}
});
```
