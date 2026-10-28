# GetParentTable

Returns a parent table of the current cell.

## Syntax

```javascript
expression.GetParentTable();
```

`expression` - A variable that represents an [ApiTableCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable.md) \| null

## Example

Get the parent table of a table cell in a PDF.

```javascript editor-pdf
// Access the table that contains a given cell in a PDF.

// Get the parent table and change its background color in a PDF.

const doc = Api.GetDocument();
const page = doc.GetPage(0);

const table = Api.CreateTable(2, 3);
const cell = table.GetRow(0).GetCell(0);
const parentTable = cell.GetParentTable();
parentTable.SetBackgroundColor(Api.RGB(51, 133, 255));

page.AddObject(table);
```
