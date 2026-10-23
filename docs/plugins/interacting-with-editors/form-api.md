# Form API

The Form API lists the methods and events a plugin can use when working with a form in ONLYOFFICE Docs. To work with the form content directly, such as form fields, run Office API code in `callCommand`. See [Form API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/AddOleObject.md) | None | Adds an OLE object to the current document position. |
| [CoAuthoringChatSendMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/CoAuthoringChatSendMessage.md) | None | Sends a message to the co-authoring chat. |
| [ConvertDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/ConvertDocument.md) | string | Converts a document to Markdown or HTML text. |
| [EditOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/EditOleObject.md) | None | Edits an OLE object in the document. |
| [EndAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/EndAction.md) | None | Specifies the end action for long operations. |
| [FocusEditor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/FocusEditor.md) | None | Returns focus to the editor. |
| [GetAllForms](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetAllForms.md) | [ContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Enumeration/ContentControl.md)[] | Returns information about all the forms that have been added to the document. |
| [GetDocumentLang](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetDocumentLang.md) | string | Returns the document language. |
| [GetFileToDownload](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetFileToDownload.md) | string | Returns the current file to download in the specified format. |
| [GetFontList](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetFontList.md) | [FontInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Enumeration/FontInfo.md)[] | Returns the fonts list. |
| [GetFormValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetFormValue.md) | null \| string \| boolean | Returns a value of the specified form. |
| [GetFormsByTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetFormsByTag.md) | [ContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Enumeration/ContentControl.md)[] | Returns information about all the forms that have been added to the document with specified tag. |
| [GetImageDataFromSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetImageDataFromSelection.md) | [ImageData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Enumeration/ImageData.md) \| null \| undefined | Returns the image data from the first of the selected drawings. |
| [GetInstalledPlugins](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetInstalledPlugins.md) | [PluginData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Enumeration/PluginData.md)[] | Returns all the installed plugins. |
| [GetMacros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetMacros.md) | [Macros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Enumeration/Macros.md) | Returns the document macros. |
| [GetOFormRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetOFormRole.md) | string | Returns the current role name for the OForm document. |
| [GetRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetRestrictions.md) | [EditorRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Enumeration/EditorRestrictions.md) | Returns the restrictions the editor currently applies to the document. |
| [GetSelectedContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetSelectedContent.md) | string | Returns the selected content in the specified format. |
| [GetSelectedOleObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetSelectedOleObjects.md) | [OLEProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Enumeration/OLEProperties.md)[] | Returns an array of the selected OLE objects. |
| [GetSelectedText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetSelectedText.md) | string | Returns the selected text from the document. |
| [GetSelectionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetSelectionType.md) | [SelectionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Enumeration/SelectionType.md) | Returns the type of the current selection. |
| [GetVBAMacros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetVBAMacros.md) | string \| null | Returns all VBA macros from the document. |
| [GetVersion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetVersion.md) | string | Returns the editor version. |
| [InputText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/InputText.md) | None | Inserts text into the document. |
| [InstallPlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/InstallPlugin.md) | object | Installs a plugin using the specified plugin config. |
| [IsEditingPdfForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/IsEditingPdfForm.md) | boolean | Checks if the document is in the editing PDF form mode. |
| [IsFillingForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/IsFillingForm.md) | boolean | Checks if the document is in the filling form mode. |
| [IsFillingPdfForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/IsFillingPdfForm.md) | boolean | Checks if the document is in the filling PDF form mode. |
| [IsFormSigned](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/IsFormSigned.md) | boolean | Checks whether the specified form has been digitally signed. |
| [MouseMoveWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/MouseMoveWindow.md) | None | Sends an event to the plugin when the mouse button is moved inside the plugin iframe. |
| [MouseUpWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/MouseUpWindow.md) | None | Sends an event to the plugin when the mouse button is released inside the plugin iframe. |
| [OnDropEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/OnDropEvent.md) | None | Implements the external drag&drop emulation. |
| [OnEncryption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/OnEncryption.md) | None | Encrypts the document. |
| [PasteHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/PasteHtml.md) | None | Pastes text in the HTML format into the document. |
| [PasteText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/PasteText.md) | None | Pastes text into the document. |
| [PutImageDataToSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/PutImageDataToSelection.md) | None | Replaces the first selected drawing with the image specified in the parameters. |
| [RemovePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/RemovePlugin.md) | object | Removes a plugin with the specified GUID. |
| [ReplaceTextSmart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/ReplaceTextSmart.md) | boolean | Replaces each paragraph (or text in cell) in the select with the corresponding text from an array of strings. |
| [SetFormValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/SetFormValue.md) | None | Sets a value to the specified form. |
| [SetMacros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/SetMacros.md) | None | Sets macros to the document. |
| [SetPluginsOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/SetPluginsOptions.md) | None | Configures plugins from an external source. |
| [SetProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/SetProperties.md) | None | Sets the properties to the document. |
| [ShowButton](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/ShowButton.md) | None | Shows or hides buttons in the header. |
| [ShowError](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/ShowError.md) | None | Shows an error/warning message. |
| [ShowInputHelper](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/ShowInputHelper.md) | None | Shows the input helper. |
| [StartAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/StartAction.md) | None | Specifies the start action for long operations. |
| [UnShowInputHelper](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/UnShowInputHelper.md) | None | Unshows the input helper. |
| [UpdatePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/UpdatePlugin.md) | object | Updates a plugin using the specified plugin config. |

## Events

The following table lists the available events.

| Event | Description |
| ----- | ----------- |
| [onChangeRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Events/onChangeRestrictions.md) | The function called when the restrictions in the editor are changed. |
| [onClick](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Events/onClick.md) | The function called when the user clicks the element. |
| [onDocumentContentReady](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Events/onDocumentContentReady.md) | The function called when the document is completely loaded. |
| [onEnableMouseEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Events/onEnableMouseEvent.md) | The function called to turn the mouse or touchpad events on/off. |
| [onExternalMouseUp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Events/onExternalMouseUp.md) | The function called when the mouse button is released outside the plugin iframe. |
| [onFloatActionButtonClick](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Events/onFloatActionButtonClick.md) | The function called when the floating action button has been clicked. |
| [onSubmitForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Events/onSubmitForm.md) | The function called when the user clicks the "Complete & Submit" button. |
| [onTargetPositionChanged](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Events/onTargetPositionChanged.md) | The function called when the target position in the editor is changed. |
