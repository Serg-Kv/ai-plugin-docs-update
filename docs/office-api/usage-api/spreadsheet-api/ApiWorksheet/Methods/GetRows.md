# GetRows

Returns the ApiRange object that represents all the cells on the rows range.

## Syntax

```javascript
expression.GetRows(value);
```

`expression` - A variable that represents an [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| value | Required | string \| number |  | Specifies the rows range in the string or number format. |

## Returns

[ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null

## Example

Select several rows together to style them all at once in a spreadsheet.

```javascript editor-xlsx
// Work with a group of rows when you want to apply one change everywhere in a spreadsheet?

// Color a row range uniformly by treating it as a single collection in a spreadsheet.

let worksheet = Api.GetActiveSheet();
worksheet.GetRows("1:4").SetFillColor(Api.RGB(255, 213, 191));
```
