# ApiComplexForm

Class representing a complex field.

ApiComplexForm is a subclass of [ApiFormBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase.md).

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| Value | string | Returns the current text value of the complex form. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/Add.md) | boolean | Appends the text content of the given form to the end of the current complex form. |
| [Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/Clear.md) | boolean | Clears the current form. |
| [ClearContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/ClearContent.md) | boolean | Clears all content from the current complex form, resetting it to its placeholder state. |
| [Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/Copy.md) | [ApiForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ApiForm.md) \| null \| undefined | Copies the current form (copies with the shape if it exists). |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/Delete.md) | boolean | Removes a form and its content. |
| [GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetBackgroundColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) \| null \| undefined | Returns the background color of the current form. |
| [GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetBorderColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) \| null \| undefined | Returns the border color of the current form. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetClassType.md) | "form" | Returns a type of the ApiComplexForm class. |
| [GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetFormKey.md) | string | Returns the current form key. |
| [GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetFormType.md) | [FormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/FormType.md) | Returns a type of the current form. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetInternalId.md) | string | Returns an internal id of the current form. |
| [GetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetLock.md) | boolean | Returns the lock state of the current form. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetParent.md) | [ParagraphLikeContainer](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ParagraphLikeContainer.md) \| null \| undefined | Returns the parent element (a paragraph or an inline content control) that directly contains the current form. |
| [GetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetPlaceholderText.md) | string | Returns the placeholder text from the current form. |
| [GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetPosInParent.md) | Number | Returns the position (index) of the current form within its parent element. |
| [GetRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetRole.md) | string | Returns the role of the current form. |
| [GetSubForms](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetSubForms.md) | [ApiForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ApiForm.md)[] | Returns an ordered list of subforms. |
| [GetTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetTag.md) | string | Returns the tag attribute for the current form. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetText.md) | string | Returns the text from the current form. |
| [GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetTextPr.md) | [ApiTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr.md) | Returns the text properties from the current form. |
| [GetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetTipText.md) | string | Returns the tip text of the current form. |
| [GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetValue.md) | string | Returns the current text value of the complex form. |
| [GetWrapperShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetWrapperShape.md) | [ApiShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape.md) \| null \| undefined | Returns a shape in which the form is placed to control the position and size of the fixed size form frame. |
| [IsFilled](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/IsFilled.md) | boolean | Checks if the current form is filled. |
| [IsFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/IsFixed.md) | boolean | Checks if the current form is fixed size. |
| [IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/IsRequired.md) | boolean | Checks if the current form is required. |
| [MoveCursorOutside](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/MoveCursorOutside.md) | boolean | Places a cursor before/after the current form. |
| [SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/SetBackgroundColor.md) | boolean | Sets the background color to the current form. |
| [SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/SetBorderColor.md) | boolean | Sets the border color to the current form. |
| [SetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/SetFormKey.md) | boolean | Sets a key to the current form. |
| [SetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/SetLock.md) | boolean | Sets the lock state of the current form. |
| [SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/SetPlaceholderText.md) | boolean | Sets the placeholder text to the current form. |
| [SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/SetRequired.md) | boolean | Specifies if the current form should be required. |
| [SetRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/SetRole.md) | boolean | Sets the role to the current form. |
| [SetTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/SetTag.md) | boolean | Sets the tag attribute to the current form. |
| [SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/SetTextPr.md) | boolean | Sets the text properties to the current form. |
| [SetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/SetTipText.md) | boolean | Sets the tip text to the current form. |
| [SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/SetValue.md) | boolean | Sets the value of the form field. |
| [ToFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/ToFixed.md) | boolean | Converts the current form to a fixed size form. |
| [ToInline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/ToInline.md) | boolean | Converts the current form to an inline form. |
