# ApiRichRun

Class representing a small text block called 'run'.

ApiRichRun is a subclass of [ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/AddText.md) | boolean | Adds some text to the current run. |
| [ClearContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/ClearContent.md) | boolean | Clears the content from the current run. |
| [Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/Copy.md) | [ApiRichRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun.md) | Creates a copy of the current run. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/Delete.md) | boolean | Deletes the current run. |
| [GetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetBold.md) | boolean \| null \| undefined | Gets the bold property from the current text properties. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetClassType.md) | "richRun" | Returns a type of the ApiRichRun class. |
| [GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined | Gets the RGB color from the current text properties. |
| [GetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetFontFamily.md) | string \| null \| undefined | Returns the font family from the current text properties. |
| [GetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetFontSize.md) | [hps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/hps.md) \| null \| undefined | Gets the font size from the current text properties. |
| [GetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetItalic.md) | boolean \| null \| undefined | Gets the italic property from the current text properties. |
| [GetParentParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetParentParagraph.md) | [ApiRichParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph.md) \| null \| undefined | Returns a parent paragraph of the current run. |
| [GetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetStrikeout.md) | boolean \| null \| undefined | Gets the strikeout property from the current text properties. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetText.md) | string | Returns a text from the text run. |
| [GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetTextPr.md) | [ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md) | Returns the text properties of the current run. |
| [GetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetUnderline.md) | boolean \| null \| undefined | Gets the underline property from the current text properties. |
| [GetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetVertAlign.md) | [TextVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/TextVertAlign.md) | Gets the vertical alignment type from the current text properties. |
| [RemoveAllElements](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/RemoveAllElements.md) | boolean | Removes all the elements from the current run. |
| [SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetBold.md) | [ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md) | Sets the bold property to the text character. |
| [SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetColor.md) | [ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md) | Sets the text color to the current text run. |
| [SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetFontFamily.md) | [ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md) | Sets all 4 font slots with the specified font family. |
| [SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetFontSize.md) | [ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md) | Sets the font size to the characters of the current text run. |
| [SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetItalic.md) | [ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md) | Sets the italic property to the text character. |
| [SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetStrikeout.md) | [ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md) | Specifies that the contents of the run are displayed with a single horizontal line through the center of the line. |
| [SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetTextPr.md) | [ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md) | Sets the text properties to the current run. |
| [SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetUnderline.md) | [ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md) | Specifies that the contents of the run are displayed along with a line appearing directly below the character (less than all the spacing above and below the characters on the line). |
| [SetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetVertAlign.md) | [ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md) | Specifies the alignment which will be applied to the contents of the run in relation to the default appearance of the run text: |
