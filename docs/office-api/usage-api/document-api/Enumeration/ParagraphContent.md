# ParagraphContent

The types of elements that can be added to the paragraph structure.

## Type

Enumeration

## Values

- [ApiUnsupported](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiUnsupported.md)
- [ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun.md)
- [ApiInlineLvlSdt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt.md)
- [ApiHyperlink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiHyperlink.md)
- [ApiFormBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase.md)
- [ApiMath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiMath.md)

## Example

Add an element called 'text run' to the paragraph.

```javascript editor-docx
// How do I add an element to a paragraph?

// Insert an element to paragraph.

paragraph.AddElement(run, 0);
```
