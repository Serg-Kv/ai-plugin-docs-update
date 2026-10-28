# TYPE

Returns an integer representing the data type of a value: number = 1; text = 2; logical value = 4; error value = 16; array = 64; compound data = 128.

## Syntax

```javascript
expression.TYPE(arg1);
```

`expression` - A variable that represents an [ApiWorksheetFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| arg1 | Required | number \| string \| boolean \| (number \| string \| boolean)[] \| [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| [ApiName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiName.md) |  | A value to test. |

## Returns

number

## Example

Identify the data type of a cell value and return a numeric code in a spreadsheet.

```javascript editor-xlsx
// How do I determine what type of data is stored in a cell in a spreadsheet?

// Get a numeric identifier that indicates whether a value is text, a number, or a boolean in a spreadsheet.

let worksheet = Api.GetActiveSheet();
let func = Api.WorksheetFunction;
worksheet.GetRange("A1").SetValue(func.TYPE(255));
worksheet.GetRange("A2").SetValue(func.TYPE(true));
worksheet.GetRange("A3").SetValue(func.TYPE("Online Office"));
```
