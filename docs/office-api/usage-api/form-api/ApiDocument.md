# ApiDocument

Class representing a document.

ApiDocument is a subclass of [ApiDocumentContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [ClearAllFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/ClearAllFields.md) | boolean | Clears all forms in the document. |
| [GetAllForms](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetAllForms.md) | [ApiForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/ApiForm.md)[] | Returns all existing forms in the document. |
| [GetFormKeysByRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetFormKeysByRole.md) | string[] | Returns a list of all form keys attached to the specified role. |
| [GetFormRoles](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetFormRoles.md) | [ApiFormRoles](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormRoles.md) | Returns a collection of form roles. |
| [GetFormValueByKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetFormValueByKey.md) | null \| boolean \| string | Returns the form value for the specified key. |
| [GetFormsByKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetFormsByKey.md) | [ApiForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/ApiForm.md)[] | Returns a list of all forms in the document with the specified key. |
| [GetFormsByRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetFormsByRole.md) | [ApiForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/ApiForm.md)[] | Returns a list of all forms in the document with the specified role name. |
| [GetFormsByTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetFormsByTag.md) | [ApiForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/ApiForm.md)[] | Returns a list of all forms in the document with the specified tag name. |
| [GetFormsData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetFormsData.md) | [FormData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/FormData.md)[] | Returns the data from all forms present in the current document. |
| [GetFormsHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetFormsHighlight.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) \| null | Returns the highlight color of the forms in the document. |
| [GetTagsOfAllForms](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetTagsOfAllForms.md) | String[] | Returns a list of all tags that are used for all forms in the document. |
| [InsertTextForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/InsertTextForm.md) | [ApiTextForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm.md) | Inserts a text box with the specified text box properties over the selected text. |
| [SetFormsData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/SetFormsData.md) | boolean | Sets the data to the specified forms. |
| [SetFormsHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/SetFormsHighlight.md) | boolean | Sets the highlight to the forms in the document. |
