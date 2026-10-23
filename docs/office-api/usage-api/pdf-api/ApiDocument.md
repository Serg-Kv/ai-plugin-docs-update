# ApiDocument

Class representing a document.

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/AddPage.md) | [ApiPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage.md) | Adds a new page to document. |
| [ApplyRedact](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/ApplyRedact.md) | boolean | Applies added redact. |
| [GetAllFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetAllFields.md) | [ApiField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ApiField.md)[] | Gets list of all fields in document. |
| [GetCalculateOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetCalculateOrder.md) | string[] | Gets document calculate fields order |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetClassType.md) | "document" | Returns a type of the ApiDocument class. |
| [GetFieldByName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetFieldByName.md) | [ApiField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ApiField.md) \| null \| undefined | Gets field by it's name. |
| [GetPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetPage.md) | [ApiPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage.md) | Gets page by index from document. |
| [GetPagesCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetPagesCount.md) | number | Gets document pages count |
| [GetSelectedText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetSelectedText.md) | string | Gets selected text in document |
| [GetSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetSelection.md) | [DocSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/DocSelection.md) \| null \| undefined | Gets document selection info |
| [GetSelectionQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetSelectionQuads.md) | [DocQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/DocQuads.md) | Gets document selection quads by page |
| [GetStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetStyle.md) | ApiStyle \| null | Returns the document style by its name. |
| [Merge](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/Merge.md) | boolean | Merges pdf files to current document in specified position. |
| [RemovePage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/RemovePage.md) | boolean | Removes a page from the document by its index. |
| [SearchAndRedact](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/SearchAndRedact.md) | [ApiRedactAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRedactAnnotation.md)[] | Searchs words and adds redact to it. |
| [SetCalculateOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/SetCalculateOrder.md) | boolean | Sets document calculate fields order |
| [SetSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/SetSelection.md) | boolean | Sets document selection |
| [Split](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/Split.md) | [PdfFile](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/PdfFile.md) | Splits current pdf file with specified pages. |
