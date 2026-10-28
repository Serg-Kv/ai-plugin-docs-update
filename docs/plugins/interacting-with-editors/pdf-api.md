# PDF API

The PDF API lists the methods and events a plugin can use when working with a PDF file in ONLYOFFICE Docs. To work with the PDF content directly, such as pages and annotations, run Office API code in `callCommand`. See [PDF API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [CoAuthoringChatSendMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/CoAuthoringChatSendMessage.md) | None | Sends a message to the co-authoring chat. |
| [EndAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/EndAction.md) | None | Specifies the end action for long operations. |
| [FocusEditor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/FocusEditor.md) | None | Returns focus to the editor. |
| [GetAllComments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetAllComments.md) | [comment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/comment.md)[] | Returns all the comments from the document. |
| [GetCurrentPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetCurrentPage.md) | number | Returns the current page index. |
| [GetFileToDownload](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetFileToDownload.md) | string | Returns the current file to download in the specified format. |
| [GetFontList](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetFontList.md) | [FontInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/FontInfo.md)[] | Returns the fonts list. |
| [GetInstalledPlugins](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetInstalledPlugins.md) | [PluginData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/PluginData.md)[] | Returns all the installed plugins. |
| [GetMacros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetMacros.md) | [Macros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/Macros.md) | Returns the document macros. |
| [GetPageImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetPageImage.md) | string \| Object | Returns the page image. |
| [GetRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetRestrictions.md) | [EditorRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/EditorRestrictions.md) | Returns the restrictions the editor currently applies to the document. |
| [GetSelectedText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetSelectedText.md) | string | Returns the selected text from the document. |
| [GetVersion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetVersion.md) | string | Returns the editor version. |
| [GoToPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GoToPage.md) | boolean | Moves to specified page. |
| [InstallPlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/InstallPlugin.md) | object | Installs a plugin using the specified plugin config. |
| [MouseMoveWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/MouseMoveWindow.md) | None | Sends an event to the plugin when the mouse button is moved inside the plugin iframe. |
| [MouseUpWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/MouseUpWindow.md) | None | Sends an event to the plugin when the mouse button is released inside the plugin iframe. |
| [OnDropEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/OnDropEvent.md) | None | Implements the external drag&drop emulation. |
| [PasteHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/PasteHtml.md) | None | Pastes text in the HTML format into the document. |
| [PasteText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/PasteText.md) | None | Pastes text into the document. |
| [RemovePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/RemovePlugin.md) | object | Removes a plugin with the specified GUID. |
| [ReplacePageContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/ReplacePageContent.md) | boolean | Replaces the page content with the specified parameters. |
| [SetMacros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/SetMacros.md) | None | Sets macros to the document. |
| [SetPluginsOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/SetPluginsOptions.md) | None | Configures plugins from an external source. |
| [SetProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/SetProperties.md) | None | Sets the properties to the document. |
| [ShowButton](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/ShowButton.md) | None | Shows or hides buttons in the header. |
| [ShowError](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/ShowError.md) | None | Shows an error/warning message. |
| [ShowInputHelper](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/ShowInputHelper.md) | None | Shows the input helper. |
| [StartAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/StartAction.md) | None | Specifies the start action for long operations. |
| [UnShowInputHelper](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/UnShowInputHelper.md) | None | Unshows the input helper. |
| [UpdatePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/UpdatePlugin.md) | object | Updates a plugin using the specified plugin config. |

## Events

The following table lists the available events.

| Event | Description |
| ----- | ----------- |
| [onChangeRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onChangeRestrictions.md) | The function called when the restrictions in the editor are changed. |
| [onClick](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onClick.md) | The function called when the user clicks the element. |
| [onDocumentContentReady](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onDocumentContentReady.md) | The function called when the document is completely loaded. |
| [onEnableMouseEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onEnableMouseEvent.md) | The function called to turn the mouse or touchpad events on/off. |
| [onExternalMouseUp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onExternalMouseUp.md) | The function called when the mouse button is released outside the plugin iframe. |
| [onFloatActionButtonClick](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onFloatActionButtonClick.md) | The function called when the floating action button has been clicked. |
| [onSelectionCancel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onSelectionCancel.md) | The function called was when selection was canceled. |
| [onSelectionEnd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onSelectionEnd.md) | The function called to when selection was ended. |
| [onTargetPositionChanged](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onTargetPositionChanged.md) | The function called when the target position in the editor is changed. |
