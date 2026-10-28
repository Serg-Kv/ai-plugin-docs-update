# AddPage

Adds a new page to document.

## Syntax

```javascript
expression.AddPage(index, width, height);
```

`expression` - A variable that represents an [ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| index | Optional | number | this.GetPagesCount() | The index where the page will be added. |
| width | Optional | [pt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/pt.md) |  | The page width. |
| height | Optional | [pt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/pt.md) |  | The page height. |

## Returns

[ApiPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage.md)

## Example

Insert a new page into a document in a PDF.

```javascript editor-pdf
// Can I add pages to a PDF document?

// Place additional pages at specific positions in a PDF.

let doc = Api.GetDocument();
doc.AddPage(0);
```
