# INT

Rounds a number down to the nearest integer.

## Syntax

```javascript
expression.INT(arg1);
```

`expression` - A variable that represents an [ApiWorksheetFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| arg1 | Required | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| [ApiName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiName.md) \| number |  | The real number to round down to an integer. |

## Returns

number

## Example

Round a number down to the nearest integer in a spreadsheet.

```javascript editor-xlsx
// How do I round down a decimal number in a spreadsheet?

// Truncate decimal places from a number in a spreadsheet.

let worksheet = Api.GetActiveSheet();
let func = Api.WorksheetFunction;
worksheet.GetRange("A1").SetValue(func.INT(2.3));
```
