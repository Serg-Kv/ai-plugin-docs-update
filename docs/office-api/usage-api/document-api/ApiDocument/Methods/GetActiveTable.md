# GetActiveTable

Return current table from the current document.

## Syntax

```javascript
expression.GetActiveTable();
```

`expression` - A variable that represents an [ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable.md) \| null

## Example

Retrieve the table that currently contains the cursor in a document.

```javascript editor-docx
// GetActiveTable returns an ApiTable object when the cursor is inside a table, or null otherwise.

// Create a table, move the cursor into it, then get the active table to read its row count.

let doc = Api.GetDocument();
let tableStyle = doc.CreateStyle("CustomTableStyle", "table");
tableStyle.SetBasedOn(doc.GetStyle("Bordered"));
let table = Api.CreateTable(3, 3);
table.SetWidth("percent", 100);
table.SetStyle(tableStyle);
doc.Push(table);
doc.MoveCursorDown(1);
let activeTable = doc.GetActiveTable();
let paragraph = Api.CreateParagraph();
paragraph.AddText(activeTable ? "Active table rows: " + activeTable.GetRowsCount() : "No active table.");
doc.Push(paragraph);
```
