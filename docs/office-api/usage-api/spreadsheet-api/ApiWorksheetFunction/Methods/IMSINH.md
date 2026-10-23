# IMSINH

Returns the hyperbolic sine of a complex number.

## Syntax

```javascript
expression.IMSINH(arg1);
```

`expression` - A variable that represents an [ApiWorksheetFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| arg1 | Required | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| [ApiName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiName.md) \| number \| string |  | A complex number expressed in the *x + yi* or *x + yj* form. |

## Returns

string

## Example

Calculate the hyperbolic sine of a complex number in a spreadsheet.

```javascript editor-xlsx
// How do I find the hyperbolic sine value of a complex number in a spreadsheet?

// Get the hyperbolic sine result for complex number calculations in a spreadsheet.

let worksheet = Api.GetActiveSheet();
let func = Api.WorksheetFunction;
worksheet.GetRange("A1").SetValue(func.IMSINH("-2+2.5i"));
```
