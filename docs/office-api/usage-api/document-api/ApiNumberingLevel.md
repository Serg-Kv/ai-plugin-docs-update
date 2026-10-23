# ApiNumberingLevel

Class representing a reference to a specified level of the numbering.

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/GetClassType.md) | "numberingLevel" | Returns a type of the ApiNumberingLevel class. |
| [GetLevelIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/GetLevelIndex.md) | number | Returns the level index. |
| [GetNumbering](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/GetNumbering.md) | [ApiNumbering](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumbering.md) | Returns the numbering definition. |
| [GetParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/GetParaPr.md) | [ApiParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr.md) | Returns the paragraph properties which are applied to any numbered paragraph that references the given numbering definition and numbering level. |
| [GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/GetTextPr.md) | [ApiTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr.md) | Returns the text properties which will be applied to the text in the current numbering level itself, not to the text in the subsequent paragraph. |
| [LinkWithStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/LinkWithStyle.md) | boolean | Links the specified paragraph style with the current numbering level. |
| [SetCustomType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/SetCustomType.md) | boolean | Sets your own customized numbering type. |
| [SetRestart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/SetRestart.md) | boolean | Specifies a one-based index which determines when a numbering level should restart to its starting value. |
| [SetStart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/SetStart.md) | boolean | Specifies the starting value for the numbering used by the parent numbering level within a given numbering level definition. |
| [SetSuff](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/SetSuff.md) | boolean | Specifies the content which will be added between the given numbering level text and the text of every numbered paragraph which references that numbering level. |
| [SetTemplateType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/SetTemplateType.md) | boolean | Sets one of the existing predefined numbering templates. |
