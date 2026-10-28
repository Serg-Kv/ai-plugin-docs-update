# GetParent

Returns the document that owns this collection.

:::note
This functionality is available in paid ONLYOFFICE Docs editions.
:::

## Syntax

```javascript
expression.GetParent();
```

`expression` - A variable that represents an [ApiTablesOfContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfContents.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument.md)

## Example

Get the document that owns the tables of contents collection.

```javascript editor-docx
// Obtain the tables of contents collection from the current document.

// Return the parent document that the collection belongs to.

let doc = Api.GetDocument();
let tablesOfContents = doc.GetTablesOfContents();
let parent = tablesOfContents.GetParent();
let resultParagraph = Api.CreateParagraph();
resultParagraph.AddText("Parent class type: " + parent.GetClassType());
doc.Push(resultParagraph);
```
