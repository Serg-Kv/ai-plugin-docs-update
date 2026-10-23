# MergeCells

Merges the cells in the current row.

## Syntax

```javascript
expression.MergeCells();
```

`expression` - A variable that represents an [ApiTableRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiTableCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell.md) \| null

## Example

Merge all cells in a table row in a PDF.

```javascript editor-pdf
// Combine all the cells of one row into a single cell in a PDF.

// Merge all cells of the first row in a PDF.

const doc = Api.GetDocument();
const page = doc.GetPage(0);

const table = Api.CreateTable(3, 3);
const row = table.GetRow(0);
const para = Api.CreateParagraph();
para.AddText('Merged row');
row.MergeCells();
row.GetCell(0).GetContent().Push(para);

page.AddObject(table);
```
