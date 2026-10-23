# ApiDocumentContent

Class representing a container for paragraphs and tables.

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/AddElement.md) | boolean | Adds a paragraph or a table or a blockLvl content control using its position in the document content. |
| [AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/AddText.md) | [ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun.md) | Appends the specified text to the end of the document content. |
| [GetAllParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetAllParagraphs.md) | [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph.md)[] | Returns an array of all paragraphs from the current document content. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetClassType.md) | "documentContent" | Returns a type of the ApiDocumentContent class. |
| [GetCurrentParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetCurrentParagraph.md) | [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph.md) \| null \| undefined | Returns the current paragraph where the cursor is located. |
| [GetCurrentRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetCurrentRun.md) | [ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun.md) \| null \| undefined | Returns the current run where the cursor is located. |
| [GetElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetElement.md) | [DocumentElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/DocumentElement.md) \| null \| undefined | Returns an element by its position in the document. |
| [GetElementsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetElementsCount.md) | number | Returns a number of elements in the current document. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetInternalId.md) | string | Returns an internal ID of the current document content. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetText.md) | string | Returns the inner text of the current document content object. |
| [GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetTextRange.md) | [ApiTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange.md) \| null | Returns an ApiTextRange object that represents the part of the text contained in the current document content. |
| [Push](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/Push.md) | boolean | Pushes a paragraph or a table to actually add it to the document. |
| [RemoveAllElements](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/RemoveAllElements.md) | boolean | Removes all the elements from the current document or from the current document element. |
| [RemoveElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/RemoveElement.md) | boolean | Removes an element using the position specified. |
| [SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/SetText.md) | [ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun.md) | Replaces all content of the current document content object with the specified text, preserving the formatting of the first paragraph. |
