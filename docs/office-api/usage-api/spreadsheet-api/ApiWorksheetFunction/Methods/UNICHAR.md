# UNICHAR

Returns the Unicode character referenced by the given numeric value.

## Syntax

```javascript
expression.UNICHAR(arg1);
```

`expression` - A variable that represents an [ApiWorksheetFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| arg1 | Required | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| [ApiName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiName.md) \| number |  | The Unicode number representing a character. |

## Returns

string

## Example

Return the Unicode character referenced by the given numeric value in a spreadsheet.

```javascript editor-xlsx
// The UNICHAR function converts numeric code points to their corresponding characters.

// Apply the function to obtain a character from its Unicode number in a spreadsheet.

let worksheet = Api.GetActiveSheet();
let func = Api.WorksheetFunction;
worksheet.GetRange("A1").SetValue(func.UNICHAR(378));
```
