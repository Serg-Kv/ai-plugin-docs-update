# Spreadsheet API

The Spreadsheet API lists the methods and events a plugin can use when working with a spreadsheet in ONLYOFFICE Docs. To work with the spreadsheet content directly, such as worksheets and ranges, run Office API code in `callCommand`. See [Spreadsheet API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/AddComment.md) | string \| null | Adds a comment to the workbook. |
| [AddOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/AddOleObject.md) | None | Adds an OLE object to the current document position. |
| [ChangeComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/ChangeComment.md) | boolean | Changes the specified comment. |
| [CoAuthoringChatSendMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/CoAuthoringChatSendMessage.md) | None | Sends a message to the co-authoring chat. |
| [EditOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/EditOleObject.md) | None | Edits an OLE object in the document. |
| [EndAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/EndAction.md) | None | Specifies the end action for long operations. |
| [FocusEditor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/FocusEditor.md) | None | Returns focus to the editor. |
| [GetAllComments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetAllComments.md) | [comment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Enumeration/comment.md)[] | Returns all the comments from the document. |
| [GetCustomFunctions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetCustomFunctions.md) | string | Returns a library of local custom functions. |
| [GetFileToDownload](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetFileToDownload.md) | string | Returns the current file to download in the specified format. |
| [GetFontList](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetFontList.md) | [FontInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Enumeration/FontInfo.md)[] | Returns the fonts list. |
| [GetImageDataFromSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetImageDataFromSelection.md) | [ImageData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Enumeration/ImageData.md) \| null \| undefined | Returns the image data from the first of the selected drawings. |
| [GetInstalledPlugins](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetInstalledPlugins.md) | [PluginData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Enumeration/PluginData.md)[] | Returns all the installed plugins. |
| [GetMacros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetMacros.md) | [Macros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Enumeration/Macros.md) | Returns the document macros. |
| [GetRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetRestrictions.md) | [EditorRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Enumeration/EditorRestrictions.md) | Returns the restrictions the editor currently applies to the document. |
| [GetSelectedContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetSelectedContent.md) | string | Returns the selected content in the specified format. |
| [GetSelectedOleObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetSelectedOleObjects.md) | [OLEProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Enumeration/OLEProperties.md)[] | Returns an array of the selected OLE objects. |
| [GetSelectedText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetSelectedText.md) | string | Returns the selected text from the document. |
| [GetSelectionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetSelectionType.md) | [SelectionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Enumeration/SelectionType.md) | Returns the type of the current selection. |
| [GetVBAMacros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetVBAMacros.md) | string \| null | Returns all VBA macros from the document. |
| [GetVersion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetVersion.md) | string | Returns the editor version. |
| [InputText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/InputText.md) | None | Inserts text into the document. |
| [InstallPlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/InstallPlugin.md) | object | Installs a plugin using the specified plugin config. |
| [MouseMoveWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/MouseMoveWindow.md) | None | Sends an event to the plugin when the mouse button is moved inside the plugin iframe. |
| [MouseUpWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/MouseUpWindow.md) | None | Sends an event to the plugin when the mouse button is released inside the plugin iframe. |
| [OnDropEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/OnDropEvent.md) | None | Implements the external drag&drop emulation. |
| [OnEncryption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/OnEncryption.md) | None | Encrypts the document. |
| [PasteHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/PasteHtml.md) | None | Pastes text in the HTML format into the document. |
| [PasteText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/PasteText.md) | None | Pastes text into the document. |
| [PutImageDataToSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/PutImageDataToSelection.md) | None | Replaces the first selected drawing with the image specified in the parameters. |
| [RemoveComments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/RemoveComments.md) | None | Removes the specified comments. |
| [RemoveOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/RemoveOleObject.md) | None | Removes the OLE object from the workbook by its internal ID. |
| [RemovePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/RemovePlugin.md) | object | Removes a plugin with the specified GUID. |
| [ReplaceTextSmart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/ReplaceTextSmart.md) | boolean | Replaces each paragraph (or text in cell) in the select with the corresponding text from an array of strings. |
| [SetButtonDisabled](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/SetButtonDisabled.md) | None | Enables or disables the modal plugin footer button by index. |
| [SetCustomFunctions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/SetCustomFunctions.md) | None | Updates a library of local custom functions. |
| [SetMacros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/SetMacros.md) | None | Sets macros to the document. |
| [SetPluginsOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/SetPluginsOptions.md) | None | Configures plugins from an external source. |
| [SetProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/SetProperties.md) | None | Sets the properties to the document. |
| [ShowButton](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/ShowButton.md) | None | Shows or hides buttons in the header. |
| [ShowError](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/ShowError.md) | None | Shows an error/warning message. |
| [ShowInputHelper](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/ShowInputHelper.md) | None | Shows the input helper. |
| [StartAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/StartAction.md) | None | Specifies the start action for long operations. |
| [UnShowInputHelper](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/UnShowInputHelper.md) | None | Unshows the input helper. |
| [UpdatePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/UpdatePlugin.md) | object | Updates a plugin using the specified plugin config. |

## Events

The following table lists the available events.

| Event | Description |
| ----- | ----------- |
| [onChangeCurrentSheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Events/onChangeCurrentSheet.md) | The function called when the current sheet has changed. |
| [onChangeRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Events/onChangeRestrictions.md) | The function called when the restrictions in the editor are changed. |
| [onClick](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Events/onClick.md) | The function called when the user clicks the element. |
| [onDocumentContentReady](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Events/onDocumentContentReady.md) | The function called when the document is completely loaded. |
| [onEnableMouseEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Events/onEnableMouseEvent.md) | The function called to turn the mouse or touchpad events on/off. |
| [onExternalMouseUp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Events/onExternalMouseUp.md) | The function called when the mouse button is released outside the plugin iframe. |
| [onFloatActionButtonClick](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Events/onFloatActionButtonClick.md) | The function called when the floating action button has been clicked. |
| [onTargetPositionChanged](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Events/onTargetPositionChanged.md) | The function called when the target position in the editor is changed. |
