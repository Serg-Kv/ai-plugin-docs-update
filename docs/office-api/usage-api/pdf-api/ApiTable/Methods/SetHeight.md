# SetHeight

Sets the total height of the current table, distributing it evenly among the table rows. The value is applied as a minimum height for each row, so a row can be taller if its content requires more space.

## Syntax

```javascript
expression.SetHeight(nValue);
```

`expression` - A variable that represents an [ApiTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| nValue | Required | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/EMU.md) |  | The table height in English measure units. |

## Returns

[EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/EMU.md) \| null

## Example

Set the total height of a table in a PDF.

```javascript editor-pdf
// Make a table a specific overall height in a PDF.

// Distribute the requested height proportionally among the table rows in a PDF.

const doc = Api.GetDocument();
const page = doc.GetPage(0);

const table = Api.CreateTable(3, 3);
page.AddObject(table);
table.SetHeight(Api.MillimetersToEmus(80));
```
