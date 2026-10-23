# GetCustomFunctions

Returns a library of local custom functions.

## Syntax

```javascript
expression.GetCustomFunctions();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

string

## Example

```javascript
window.Asc.plugin.executeMethod ("GetCustomFunctions", null, function (res) {
    console.log ("First custom function: " + res[0])
});
```
