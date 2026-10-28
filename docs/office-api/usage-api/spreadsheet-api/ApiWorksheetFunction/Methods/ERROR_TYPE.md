# ERROR_TYPE

Returns a number matching an error value.

## Syntax

```javascript
expression.ERROR_TYPE(arg1);
```

`expression` - A variable that represents an [ApiWorksheetFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| arg1 | Required | [ErrorValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ErrorValue.md) \| [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| [ApiName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiName.md) |  | The error value for which the identifying number will be returned. It can be an actual error value or a reference to a cell containing an error value. |

## Returns

number

## Example

Return a number matching an error value in a spreadsheet.

```javascript editor-xlsx
// Get the error type code from the value.

// Identify error types using ERROR_TYPE function in a spreadsheet.

const worksheet = Api.GetActiveSheet();
let func = Api.WorksheetFunction;
let nonPositiveNum = 0;
let logResult = func.LOG(nonPositiveNum);
worksheet.GetRange("B3").SetValue(logResult);
worksheet.GetRange("C3").SetValue(func.ERROR_TYPE(logResult));
```
