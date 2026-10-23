# GetCurrentParagraph

Returns the current paragraph where the cursor is located.

Inherited from [ApiDocumentContent.GetCurrentParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetCurrentParagraph.md).

## Syntax

```javascript
expression.GetCurrentParagraph();
```

`expression` - A variable that represents an [ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md) \| null \| undefined

## Example

Access the paragraph where the cursor is placed in a document.

```javascript editor-docx
// How do I get the paragraph at the current cursor position in a document?

// Apply bold formatting to the paragraph the user is actively editing in a document.

const doc = Api.GetDocument();
const paragraph = doc.GetCurrentParagraph();
paragraph.AddText('This is current paragraph');
paragraph.SetBold(true);
```
