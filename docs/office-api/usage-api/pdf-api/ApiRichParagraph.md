# ApiRichParagraph

Class representing a rich paragraph.

ApiRichParagraph is a subclass of [ApiRichParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParaPr.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/AddElement.md) | boolean | Adds an element to the current paragraph. |
| [AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/AddText.md) | [ApiRichRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun.md) | Adds some text to the current paragraph. |
| [Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/Copy.md) | [ApiRichParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph.md) | Creates a paragraph copy. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/Delete.md) | boolean | Deletes the current paragraph. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetClassType.md) | "richParagraph" | Returns a type of the ApiRichParagraph class. |
| [GetElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetElement.md) | [ApiRichRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun.md) \| null \| undefined | Returns a paragraph element using the position specified. |
| [GetElementsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetElementsCount.md) | number | Returns a number of elements in the current paragraph. |
| [GetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetJc.md) | [HorTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/HorTextAlign.md) | Returns the rich paragraph contents justification. |
| [GetLastRunWithText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetLastRunWithText.md) | [ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun.md) | Returns the last Run with text in the current paragraph. |
| [GetNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetNext.md) | [ApiRichParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph.md) \| null \| undefined | Returns the next paragraph. |
| [GetParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetParaPr.md) | [ApiRichParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParaPr.md) | Returns the paragraph properties. |
| [GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetPosInParent.md) | Number | Returns the paragraph position within its parent element. |
| [GetPrevious](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetPrevious.md) | [ApiRichParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph.md) \| null \| undefined | Returns the previous paragraph. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetText.md) | string | Returns the paragraph text. |
| [Last](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/Last.md) | [ApiRichRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun.md) | Returns the last element of the paragraph. |
| [Push](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/Push.md) | boolean | Adds an element to the current paragraph. |
| [RemoveAllElements](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/RemoveAllElements.md) | boolean | Removes all the elements from the current paragraph. |
| [RemoveElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/RemoveElement.md) | boolean | Removes an element using the position specified. |
| [SetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/SetJc.md) | boolean | Sets the rich paragraph contents justification. |
| [SetParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/SetParaPr.md) | boolean | Sets the paragraph properties. |
| [SetReadingOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/SetReadingOrder.md) | [ApiRichParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph.md) | Specifies the reading order for the current paragraph. |
