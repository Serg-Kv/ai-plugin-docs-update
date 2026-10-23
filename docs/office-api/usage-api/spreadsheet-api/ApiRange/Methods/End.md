# End

Returns a Range object that represents the end in the specified direction in the specified range.

## Syntax

```javascript
expression.End(direction);
```

`expression` - A variable that represents an [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| direction | Required | [Direction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/Direction.md) |  | The direction of end in the specified range. * |

## Returns

[ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md)

## Example

Jump to the last occupied cell in a chosen direction within a range in a spreadsheet.

```javascript editor-xlsx
// How do I find the boundary cell of a data block by moving in a specific direction in a spreadsheet?

// Locate the edge of filled cells going left, right, up, or down and highlight it in a spreadsheet.

let worksheet = Api.GetActiveSheet();
let range = worksheet.GetRange("C4:D5");
range.End("xlToLeft").SetFillColor(Api.RGB(255, 213, 191));
```
