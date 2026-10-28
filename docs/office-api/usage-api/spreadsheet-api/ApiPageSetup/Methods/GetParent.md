# GetParent

Returns the worksheet that owns this page setup.

## Syntax

```javascript
expression.GetParent();
```

`expression` - A variable that represents an [ApiPageSetup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md)

## Example

Get the worksheet that a page setup belongs to in a spreadsheet.

```javascript editor-xlsx
// How do I get back to the worksheet from its page setup object in a spreadsheet?

// Access the parent worksheet of a page setup to read or change other sheet settings in a spreadsheet.

let worksheet = Api.GetActiveSheet();
let pageSetup = worksheet.GetPageSetup();
let parent = pageSetup.GetParent();
parent.GetRange("A1").SetValue("Parent sheet: " + parent.GetName());
```
