# SetBackgroundColor

Sets the background color to all cells in the current table row.

## Syntax

```javascript
expression.SetBackgroundColor(color);
```

`expression` - A variable that represents an [ApiTableRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableRow.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| color | Optional | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) |  | If not passed, the background color will be cleared. |

## Returns

boolean

## Example

Apply a background color to every cell in a table row in a document.

```javascript editor-docx
// How do I fill a table row with a specific background color in a document?

// Highlight an entire row by painting its cells with a chosen color in a document.

let doc = Api.GetDocument();
let tableStyle = doc.CreateStyle("CustomTableStyle", "table");
tableStyle.SetBasedOn(doc.GetStyle("Bordered"));
let table = Api.CreateTable(4, 4);
table.SetWidth("percent", 100);
table.SetStyle(tableStyle);
let tableRow = table.GetRow(1);
tableRow.SetBackgroundColor(Api.HexColor('#FF6F3D'));
doc.Push(table);
```
