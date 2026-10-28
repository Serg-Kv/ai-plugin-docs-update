# GetSection

Returns the paragraph section.

## Syntax

```javascript
expression.GetSection();
```

`expression` - A variable that represents an [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiSection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection.md)

## Example

Retrieve the section that contains a given paragraph in a document.

```javascript editor-docx
// How do I find the section a paragraph belongs to in a document?

// Resize the page by accessing the section through one of its paragraphs in a document.

let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);
paragraph.AddText("This is a new paragraph.");
let section = paragraph.GetSection();
section.SetPageSize(7200, 4320);
```
