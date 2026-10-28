# SetCellBorderLeft

Sets the border which will be displayed to the left of the current table cell.

Inherited from [ApiTableCellPr.SetCellBorderLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableCellPr/Methods/SetCellBorderLeft.md).

## Syntax

```javascript
expression.SetCellBorderLeft(type, size, space, color);
```

`expression` - A variable that represents an [ApiTableCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableCell.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| type | Required | [BorderType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/BorderType.md) |  | The cell left border style. |
| size | Required | [pt_8](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/pt_8.md) |  | The width of the current cell left border measured in eighths of a point. |
| space | Required | [pt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/pt.md) |  | The spacing offset in the left part of the table cell measured in points used to place this border. |
| color | Required | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) |  | The border color. |

## Returns

boolean

## Example

Add a border along the left edge of a table cell in a document.

```javascript editor-docx
// How do I draw a line on the left side of a table cell in a document?

// Give a cell a visible left border to separate it from the column beside it in a document.

let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);
paragraph.AddText("We create a 3x3 table and add the left 4 point black border to cell #1:");
let tableStyle = doc.CreateStyle("CustomTableStyle", "table");
tableStyle.SetBasedOn(doc.GetStyle("Bordered"));
let table = Api.CreateTable(3, 3);
table.SetWidth("percent", 100);
let cell = table.GetRow(0).GetCell(0);
cell.SetCellBorderLeft("single", 32, 0, Api.Color(51, 51, 51));
table.SetStyle(tableStyle);
doc.Push(table);
```
