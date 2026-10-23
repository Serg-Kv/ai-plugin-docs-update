# GetReferenceStyle

Returns the cell reference style.

## Syntax

```javascript
expression.GetReferenceStyle();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ReferenceStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ReferenceStyle.md)

## Example

Read the current cell addressing style and display it in a cell in a spreadsheet.

```javascript editor-xlsx
// How do I check whether the column-letter or column-number addressing style is active in a spreadsheet?

// Record the active cell reference notation into a cell for inspection in a spreadsheet.

let worksheet = Api.GetActiveSheet();
worksheet.GetRange("A1").SetValue(Api.GetReferenceStyle());
```
