# GetFontList

Returns the fonts list.

## Syntax

```javascript
expression.GetFontList();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[FontInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Enumeration/FontInfo.md)[]

## Example

```javascript
window.Asc.plugin.executeMethod ("GetFontList", null, function (res) {
    console.log (res)
});
```
