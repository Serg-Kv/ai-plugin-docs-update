# ApiTextForm

Class representing a document text field.

ApiTextForm is a subclass of [ApiFormBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase.md).

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| Value | string | Returns or sets the current text value of the text form. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/Clear.md) | boolean | Clears the current form. |
| [Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/Copy.md) | [ApiForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ApiForm.md) \| null \| undefined | Copies the current form (copies with the shape if it exists). |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/Delete.md) | boolean | Removes a form and its content. |
| [GetAllowedSymbols](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetAllowedSymbols.md) | string | Returns the allowed symbols for the current text field. |
| [GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetBackgroundColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) \| null \| undefined | Returns the background color of the current form. |
| [GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetBorderColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) \| null \| undefined | Returns the border color of the current form. |
| [GetCharactersLimit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetCharactersLimit.md) | number | Returns a limit of the text field characters. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetClassType.md) | "textForm" | Returns a type of the ApiTextForm class. |
| [GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetFormKey.md) | string | Returns the current form key. |
| [GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetFormType.md) | [FormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/FormType.md) | Returns a type of the current form. |
| [GetFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetFormat.md) | [TextFormFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/TextFormFormat.md) | Returns the format of the current text field. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetInternalId.md) | string | Returns an internal id of the current form. |
| [GetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetLock.md) | boolean | Returns the lock state of the current form. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetParent.md) | [ParagraphLikeContainer](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ParagraphLikeContainer.md) \| null \| undefined | Returns the parent element (a paragraph or an inline content control) that directly contains the current form. |
| [GetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetPlaceholderText.md) | string | Returns the placeholder text from the current form. |
| [GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetPosInParent.md) | Number | Returns the position (index) of the current form within its parent element. |
| [GetRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetRole.md) | string | Returns the role of the current form. |
| [GetTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetTag.md) | string | Returns the tag attribute for the current form. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetText.md) | string | Returns the text from the current form. |
| [GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetTextPr.md) | [ApiTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr.md) | Returns the text properties from the current form. |
| [GetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetTipText.md) | string | Returns the tip text of the current form. |
| [GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetValue.md) | string | Returns the current text value of the text form. |
| [GetWrapperShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetWrapperShape.md) | [ApiShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape.md) \| null \| undefined | Returns a shape in which the form is placed to control the position and size of the fixed size form frame. |
| [IsAutoFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/IsAutoFit.md) | boolean | Checks if the text field content is autofit, i.e. whether the font size adjusts to the size of the fixed size form. |
| [IsComb](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/IsComb.md) | boolean | Checks if the text field is a comb of characters with the same cell width. |
| [IsFilled](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/IsFilled.md) | boolean | Checks if the current form is filled. |
| [IsFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/IsFixed.md) | boolean | Checks if the current form is fixed size. |
| [IsMultiline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/IsMultiline.md) | boolean | Checks if the current text field is multiline. |
| [IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/IsRequired.md) | boolean | Checks if the current form is required. |
| [MoveCursorOutside](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/MoveCursorOutside.md) | boolean | Places a cursor before/after the current form. |
| [SetAllowedSymbols](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetAllowedSymbols.md) | boolean | Sets the allowed symbols for the current text field. |
| [SetAutoFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetAutoFit.md) | boolean | Specifies if the text field content should be autofit, i.e. whether the font size adjusts to the size of the fixed size form. |
| [SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetBackgroundColor.md) | boolean | Sets the background color to the current form. |
| [SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetBorderColor.md) | boolean | Sets the border color to the current form. |
| [SetCellWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetCellWidth.md) | boolean | Sets the cell width to the applied comb of characters. |
| [SetCharactersLimit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetCharactersLimit.md) | boolean | Sets a limit to the text field characters. |
| [SetComb](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetComb.md) | boolean | Specifies if the text field should be a comb of characters with the same cell width. |
| [SetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetFormKey.md) | boolean | Sets a key to the current form. |
| [SetFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetFormat.md) | boolean | Sets the format for the current text field. |
| [SetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetLock.md) | boolean | Sets the lock state of the current form. |
| [SetMultiline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetMultiline.md) | boolean | Specifies if the current text field should be miltiline. |
| [SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetPlaceholderText.md) | boolean | Sets the placeholder text to the current form. |
| [SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetRequired.md) | boolean | Specifies if the current form should be required. |
| [SetRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetRole.md) | boolean | Sets the role to the current form. |
| [SetTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetTag.md) | boolean | Sets the tag attribute to the current form. |
| [SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetText.md) | boolean | Sets the text to the current text field. |
| [SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetTextPr.md) | boolean | Sets the text properties to the current form. |
| [SetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetTipText.md) | boolean | Sets the tip text to the current form. |
| [SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetValue.md) | boolean | Sets the text value of the text form. |
| [ToFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/ToFixed.md) | boolean | Converts the current form to a fixed size form. |
| [ToInline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/ToInline.md) | boolean | Converts the current form to an inline form. |
