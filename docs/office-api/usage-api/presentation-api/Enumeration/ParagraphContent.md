# ParagraphContent

The types of elements that can be added to the paragraph structure.

## Type

Enumeration

## Values

- [ApiUnsupported](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiUnsupported.md)
- [ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiRun.md)
- [ApiHyperlink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiHyperlink.md)

## Example

Add an element called 'text run' to the paragraph.

```javascript editor-pptx
// How do I add an element to a paragraph?

// Insert an element to paragraph.

paragraph.AddElement(run, 0);
```
