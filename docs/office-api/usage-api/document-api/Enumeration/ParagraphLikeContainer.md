# ParagraphLikeContainer

A paragraph-like container that can directly hold inline-level content (Hyperlink, InlineLvlSdt, etc.).

## Type

Enumeration

## Values

- [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md)
- [ApiInlineLvlSdt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt.md)
- [ApiHyperlink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiHyperlink.md)
- [ApiFormBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase.md)

## Example

Get the paragraph-like container (a paragraph or an inline content control) that holds a hyperlink.

```javascript editor-docx
// The parent is a paragraph or an inline content control that directly holds the inline element.

// Retrieve the paragraph-like parent of a hyperlink.

let parent = hyperlink.GetParent();
```
