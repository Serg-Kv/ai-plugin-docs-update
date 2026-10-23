# ParagraphContent

The types of elements that can be added to the paragraph structure.

## Type

Enumeration

## Values

- [ApiUnsupported](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUnsupported.md)
- [ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRun.md)
- [ApiHyperlink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink.md)

## Example

Add an element called 'text run' to the paragraph.

```javascript editor-xlsx
// How do I add an element to a paragraph?

// Insert an element to paragraph.

paragraph.AddElement(run, 0);
```
