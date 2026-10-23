# RemoveColumn

Removes a table column with the specified cell.

## Syntax

```javascript
expression.RemoveColumn(cell);
```

`expression` - A variable that represents an [ApiTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| cell | Required | [ApiTableCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell.md) |  | The table cell from the column which will be removed. |

## Returns

boolean

## Example

Remove a table column using a cell reference.

```javascript editor-pptx
// Delete a column from the table by specifying a cell within it.

// Create a table and remove a column using a cell from that column.

const presentation = Api.GetPresentation();
const slide = presentation.GetSlideByIndex(0);

const table = Api.CreateTable(2, 4);
const row = table.GetRow(0);
let cell = row.GetCell(1);
table.RemoveColumn(cell);
cell = row.GetCell(0);
const content = cell.GetContent();
const paragraph = Api.CreateParagraph();
paragraph.AddText("The second column was removed.");
content.Push(paragraph);

slide.RemoveAllObjects();
slide.AddObject(table);
```
