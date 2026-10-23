# ApiDropCap

Class representing a drop cap. A drop cap is a large initial letter that is split off from a paragraph into a separate framed paragraph.

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/Clear.md) | boolean | Removes the drop cap, merging the drop cap letter back into the paragraph text. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/GetClassType.md) | "dropCap" | Returns the type of the ApiDropCap class. |
| [GetDistanceFromText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/GetDistanceFromText.md) | [twips](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/twips.md) | Returns the distance between the drop cap and the paragraph text measured in twentieths of a point (1/1440 of an inch). |
| [GetLinesToDrop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/GetLinesToDrop.md) | number | Returns the number of lines that the drop cap occupies. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/GetParent.md) | [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md) | Returns the paragraph this drop cap was requested from: either the framed drop cap paragraph itself, or the paragraph that continues its text. |
| [GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/GetPosition.md) | "none" \| "drop" \| "margin" | Returns the drop cap type. |
| [SetDistanceFromText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/SetDistanceFromText.md) | [ApiDropCap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap.md) | Sets the distance between the drop cap and the paragraph text measured in twentieths of a point (1/1440 of an inch). |
| [SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/SetFontFamily.md) | [ApiDropCap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap.md) | Sets the font family of the drop cap letter. |
| [SetLinesToDrop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/SetLinesToDrop.md) | [ApiDropCap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap.md) | Sets the number of lines that the drop cap occupies. The drop cap letter is resized accordingly. |
| [SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/SetPosition.md) | [ApiDropCap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap.md) \| null \| undefined | Sets the drop cap type. |
