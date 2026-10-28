---
hide_table_of_contents: true
description: Insert a clickable hyperlink within paragraph text.
tags: ["Docs", "Office API", "Documents"]
---

# Inserting hyperlink into sentence

Create a document with a clickable hyperlink embedded within a regular paragraph:

- create a paragraph with text containing an embedded hyperlink ([Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api.md), [ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument.md), [ApiParagraph/AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddText.md));
- insert a hyperlink with custom anchor text that flows naturally within the sentence ([ApiRun/AddHyperlink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/AddHyperlink.md));
- apply default hyperlink styling with blue color and underline formatting ([ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun.md)).

```ts editor-docx
let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);

// Create a paragraph with embedded hyperlink
paragraph.AddText("You can find more details in the ");
paragraph.AddText("official documentation").GetRange().AddHyperlink("https://api.onlyoffice.com/", "api.onlyoffice.com");
paragraph.AddText(" which covers the API in depth. If you are getting started, it's a good idea to review the usage examples first.");

// Set paragraph alignment to left (default)
paragraph.SetJc("left");
```
