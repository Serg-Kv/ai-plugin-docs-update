# TANH

Returns the hyperbolic tangent of a number.

## Syntax

```javascript
expression.TANH(arg1);
```

`expression` - A variable that represents an [ApiWorksheetFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| arg1 | Required | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| [ApiName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiName.md) \| number |  | Any real number for which the hyperbolic tangent will be returned. |

## Returns

number

## Example

Return the hyperbolic tangent of a number in a spreadsheet.

```javascript editor-xlsx
// Calculate the hyperbolic tangent of a number using the TANH function.

// Returns the hyperbolic tangent value of the specified number.

let worksheet = Api.GetActiveSheet();
let func = Api.WorksheetFunction;
worksheet.GetRange("A1").SetValue(func.TANH(6));
```
