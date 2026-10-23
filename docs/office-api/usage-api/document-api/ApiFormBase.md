# ApiFormBase

Class representing a document form base.

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/Clear.md) | boolean | Clears the current form. |
| [Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/Copy.md) | [ApiForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ApiForm.md) \| null \| undefined | Copies the current form (copies with the shape if it exists). |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/Delete.md) | boolean | Removes a form and its content. |
| [GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetBackgroundColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) \| null \| undefined | Returns the background color of the current form. |
| [GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetBorderColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) \| null \| undefined | Returns the border color of the current form. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetClassType.md) | "form" | Returns a type of the ApiFormBase class. |
| [GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetFormKey.md) | string | Returns the current form key. |
| [GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetFormType.md) | [FormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/FormType.md) | Returns a type of the current form. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetInternalId.md) | string | Returns an internal id of the current form. |
| [GetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetLock.md) | boolean | Returns the lock state of the current form. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetParent.md) | [ParagraphLikeContainer](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ParagraphLikeContainer.md) \| null \| undefined | Returns the parent element (a paragraph or an inline content control) that directly contains the current form. |
| [GetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetPlaceholderText.md) | string | Returns the placeholder text from the current form. |
| [GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetPosInParent.md) | Number | Returns the position (index) of the current form within its parent element. |
| [GetRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetRole.md) | string | Returns the role of the current form. |
| [GetTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetTag.md) | string | Returns the tag attribute for the current form. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetText.md) | string | Returns the text from the current form. |
| [GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetTextPr.md) | [ApiTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr.md) | Returns the text properties from the current form. |
| [GetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetTipText.md) | string | Returns the tip text of the current form. |
| [GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetValue.md) | string \| boolean | Returns the current value of the form field. |
| [GetWrapperShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetWrapperShape.md) | [ApiShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape.md) \| null \| undefined | Returns a shape in which the form is placed to control the position and size of the fixed size form frame. |
| [IsFilled](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/IsFilled.md) | boolean | Checks if the current form is filled. |
| [IsFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/IsFixed.md) | boolean | Checks if the current form is fixed size. |
| [IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/IsRequired.md) | boolean | Checks if the current form is required. |
| [MoveCursorOutside](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/MoveCursorOutside.md) | boolean | Places a cursor before/after the current form. |
| [SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetBackgroundColor.md) | boolean | Sets the background color to the current form. |
| [SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetBorderColor.md) | boolean | Sets the border color to the current form. |
| [SetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetFormKey.md) | boolean | Sets a key to the current form. |
| [SetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetLock.md) | boolean | Sets the lock state of the current form. |
| [SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetPlaceholderText.md) | boolean | Sets the placeholder text to the current form. |
| [SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetRequired.md) | boolean | Specifies if the current form should be required. |
| [SetRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetRole.md) | boolean | Sets the role to the current form. |
| [SetTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetTag.md) | boolean | Sets the tag attribute to the current form. |
| [SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetTextPr.md) | boolean | Sets the text properties to the current form. |
| [SetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetTipText.md) | boolean | Sets the tip text to the current form. |
| [SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetValue.md) | boolean | Sets the value of the form field. |
| [ToFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/ToFixed.md) | boolean | Converts the current form to a fixed size form. |
| [ToInline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/ToInline.md) | boolean | Converts the current form to an inline form. |
