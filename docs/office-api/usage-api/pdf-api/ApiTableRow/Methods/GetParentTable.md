# GetParentTable

Returns the parent table of the current row.

## Syntax

```javascript
expression.GetParentTable();
```

`expression` - A variable that represents an [ApiTableRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable.md) \| null

## Example

Get the parent table of a row in a PDF.

```javascript editor-pdf
// Access the table that contains a given row in a PDF.

// Get the parent table from a row and change its background color in a PDF.

const doc = Api.GetDocument();
const page = doc.GetPage(0);

const table = Api.CreateTable(2, 3);
const row = table.GetRow(0);
const parentTable = row.GetParentTable();
parentTable.SetBackgroundColor(Api.RGB(51, 133, 255));

page.AddObject(table);
```
