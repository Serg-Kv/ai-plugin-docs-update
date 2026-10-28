# GetDocument

Creates a text field with the specified text field properties.

## Syntax

```javascript
expression.GetDocument();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument.md)

## Example

Access the document object to modify pages in a PDF.

```javascript editor-pdf
// Access the main document object in a PDF.

// Retrieve the document, add a new page, and rotate it in a PDF.

let doc = Api.GetDocument();
let page = doc.AddPage(0);
page.SetRotation(90);
```
