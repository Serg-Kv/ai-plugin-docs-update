# GetActiveSheet

Returns an object that represents the active sheet.

## Syntax

```javascript
expression.GetActiveSheet();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md)

## Example

Access the currently open sheet to read or write data in a spreadsheet.

```javascript editor-xlsx
// How do I work with the sheet that is currently visible in a spreadsheet?

// Target the active tab to place values into cells in a spreadsheet.

let worksheet = Api.GetActiveSheet();
worksheet.GetRange("B1").SetValue("2");
worksheet.GetRange("B2").SetValue("2");
worksheet.GetRange("A3").SetValue("2x2=");
worksheet.GetRange("B3").SetValue("=B1*B2");
```
