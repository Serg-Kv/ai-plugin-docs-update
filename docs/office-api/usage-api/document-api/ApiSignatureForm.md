# ApiSignatureForm

Class representing a document picture form.

ApiSignatureForm is a subclass of [ApiFormBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase.md).

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| Value | string | Returns or sets the current image of the signature form as a base64 encoded string. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/Clear.md) | boolean | Clears the current form. |
| [Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/Copy.md) | [ApiForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ApiForm.md) \| null \| undefined | Copies the current form (copies with the shape if it exists). |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/Delete.md) | boolean | Removes a form and its content. |
| [GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetBackgroundColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) \| null \| undefined | Returns the background color of the current form. |
| [GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetBorderColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) \| null \| undefined | Returns the border color of the current form. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetClassType.md) | "signatureForm" | Returns a type of the ApiSignatureForm class. |
| [GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetFormKey.md) | string | Returns the current form key. |
| [GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetFormType.md) | [FormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/FormType.md) | Returns a type of the current form. |
| [GetImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetImage.md) | [Base64Img](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/Base64Img.md) | Returns an image in the base64 format from the current signature form. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetInternalId.md) | string | Returns an internal id of the current form. |
| [GetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetLock.md) | boolean | Returns the lock state of the current form. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetParent.md) | [ParagraphLikeContainer](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ParagraphLikeContainer.md) \| null \| undefined | Returns the parent element (a paragraph or an inline content control) that directly contains the current form. |
| [GetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetPlaceholderText.md) | string | Returns the placeholder text from the current form. |
| [GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetPosInParent.md) | Number | Returns the position (index) of the current form within its parent element. |
| [GetRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetRole.md) | string | Returns the role of the current form. |
| [GetTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetTag.md) | string | Returns the tag attribute for the current form. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetText.md) | string | Returns the text from the current form. |
| [GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetTextPr.md) | [ApiTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr.md) | Returns the text properties from the current form. |
| [GetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetTipText.md) | string | Returns the tip text of the current form. |
| [GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetValue.md) | string | Returns the current image of the signature form as a base64 encoded string. |
| [GetWrapperShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetWrapperShape.md) | [ApiShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape.md) \| null \| undefined | Returns a shape in which the form is placed to control the position and size of the fixed size form frame. |
| [IsFilled](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/IsFilled.md) | boolean | Checks if the current form is filled. |
| [IsFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/IsFixed.md) | boolean | Checks if the current form is fixed size. |
| [IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/IsRequired.md) | boolean | Checks if the current form is required. |
| [MoveCursorOutside](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/MoveCursorOutside.md) | boolean | Places a cursor before/after the current form. |
| [SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetBackgroundColor.md) | boolean | Sets the background color to the current form. |
| [SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetBorderColor.md) | boolean | Sets the border color to the current form. |
| [SetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetFormKey.md) | boolean | Sets a key to the current form. |
| [SetImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetImage.md) | boolean | Sets an image to the current picture form. |
| [SetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetLock.md) | boolean | Sets the lock state of the current form. |
| [SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetPlaceholderText.md) | boolean | Sets the placeholder text to the current form. |
| [SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetRequired.md) | boolean | Specifies if the current form should be required. |
| [SetRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetRole.md) | boolean | Sets the role to the current form. |
| [SetTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetTag.md) | boolean | Sets the tag attribute to the current form. |
| [SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetTextPr.md) | boolean | Sets the text properties to the current form. |
| [SetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetTipText.md) | boolean | Sets the tip text to the current form. |
| [SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetValue.md) | boolean | Sets an image to the signature form. |
| [ToFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/ToFixed.md) | boolean | Converts the current form to a fixed size form. |
| [ToInline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/ToInline.md) | boolean | Converts the current form to an inline form. |
