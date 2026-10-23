# IMAGINARY

Returns the imaginary coefficient of a complex number.

## Syntax

```javascript
expression.IMAGINARY(arg1);
```

`expression` - A variable that represents an [ApiWorksheetFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| arg1 | Required | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| [ApiName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiName.md) \| number \| string |  | A complex number expressed in the *x + yi* or *x + yj* form. |

## Returns

number

## Example

Extract the imaginary part of a complex number in a spreadsheet.

```javascript editor-xlsx
// How do I read the imaginary coefficient in a spreadsheet?

// Find the imaginary component of a complex number in a spreadsheet.

let worksheet = Api.GetActiveSheet();
let func = Api.WorksheetFunction;
worksheet.GetRange("A1").SetValue(func.IMAGINARY("-2+2.5i"));
```
