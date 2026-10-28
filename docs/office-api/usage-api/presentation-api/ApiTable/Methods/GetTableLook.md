# GetTableLook

Gets table look properties

## Syntax

```javascript
expression.GetTableLook();
```

`expression` - A variable that represents an [ApiTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[TableLook](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/TableLook.md)

## Example

Read the visual styling options applied to a table.

```javascript editor-pptx
// Get the formatting flags that control table appearance and style.

// Create a table, apply styling flags, and read them back.

const presentation = Api.GetPresentation();
const slide = presentation.GetSlideByIndex(0);
const table = Api.CreateTable(4, 4);
table.SetTableLook(true, false, false, false, false, true);
const tableLook = table.GetTableLook();
table.GetRow(0).GetCell(0).GetContent().GetElement(0).AddText("First column: " + tableLook.firstCol);
slide.RemoveAllObjects();
slide.AddObject(table);
```
