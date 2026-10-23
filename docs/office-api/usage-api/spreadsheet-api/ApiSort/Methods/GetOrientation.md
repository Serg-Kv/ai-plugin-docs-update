# GetOrientation

Returns the sort orientation: "xlTopToBottom" or "xlLeftToRight".

:::note
This functionality is available in paid ONLYOFFICE Docs editions.
:::

## Syntax

```javascript
expression.GetOrientation();
```

`expression` - A variable that represents an [ApiSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[XlSortOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlSortOrientation.md)

## Example

Read whether a table is sorted across rows or down columns in a spreadsheet.

```javascript editor-xlsx
// How do I check the direction a sort will run — top to bottom or left to right — in a spreadsheet?

// Retrieve the axis along which the sort rearranges data in a spreadsheet.

let worksheet = Api.GetActiveSheet();
worksheet.GetRange("A1").SetValue("Product");
worksheet.GetRange("A2").SetValue("Apples");
worksheet.GetRange("A3").SetValue("Oranges");
let table = worksheet.AddListObject("xlSrcRange", "A1:A3");

let sort = table.GetSort();

worksheet.GetRange("C1").SetValue("Sort orientation:");
worksheet.GetRange("D1").SetValue(sort.GetOrientation());
```
