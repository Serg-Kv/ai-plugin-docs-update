---
sidebar_position: -1
---

# Changelog

The list of changes for ONLYOFFICE Plugins and Macros API.

## Version 10.0

- Added the global [Editor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/how-to-call-methods.md#editor-object) object to the plugins API. Editor methods are now called as functions that return a Promise, for example, `await Editor.GetSelectedText()`, instead of through `window.Asc.plugin.executeMethod`. A callback passed as the last argument is still supported.
- Added the [Editor.RunMacro](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/how-to-call-commands.md#editorrunmacro) method, which runs a function with the editor API, passes arguments to it, and returns its result as a Promise.
- Renamed the `IsFillingFormMode` method to `IsFillingForm` for [Document API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/IsFillingForm.md) and [Form API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/IsFillingForm.md). The old name still works.
- Renamed the `IsFillingOFormMode` method to `IsFillingPdfForm` for [Document API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/IsFillingPdfForm.md) and [Form API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/IsFillingPdfForm.md). The old name still works.
- Renamed the `IsEditingOFormMode` method to `IsEditingPdfForm` for [Document API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/IsEditingPdfForm.md) and [Form API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/IsEditingPdfForm.md). The old name still works.
- Added the `GetRestrictions` method for [Document API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetRestrictions.md), [Form API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetRestrictions.md), [Spreadsheet API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetRestrictions.md), [Presentation API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/GetRestrictions.md), and [PDF API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetRestrictions.md).
- Added the `SetButtonDisabled` method for [Document API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/SetButtonDisabled.md), [Spreadsheet API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/SetButtonDisabled.md), and [Presentation API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/SetButtonDisabled.md).
- Added the `GetOFormRole` method for [Document API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetOFormRole.md) and [Form API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetOFormRole.md).
- Added the [MoveCursorToAnnotationRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/MoveCursorToAnnotationRange.md) method for Document API.
- Added the [SetRangeHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/SetRangeHtml.md) method for Document API.
- Added the [InsertPresentationFromUrl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/InsertPresentationFromUrl.md) method for Presentation API.
- Added the [SetParagraphHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/SetParagraphHtml.md) method for Presentation API.
- Added the [SetParagraphRangeHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/SetParagraphRangeHtml.md) method for Presentation API.
- Added the [AnnotateParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/AnnotateParagraph.md) method for Presentation API.
- Added the [SelectAnnotationRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/SelectAnnotationRange.md) method for Presentation API.
- Added the [RemoveAnnotationRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/RemoveAnnotationRange.md) method for Presentation API.
- Added the `onFloatActionButtonClick` event for [Document API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Events/onFloatActionButtonClick.md), [Form API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Events/onFloatActionButtonClick.md), [Spreadsheet API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Events/onFloatActionButtonClick.md), [Presentation API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Events/onFloatActionButtonClick.md), and [PDF API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onFloatActionButtonClick.md).
- Added the [onSelectionEnd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onSelectionEnd.md) event for PDF API.
- Added the [onSelectionCancel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Events/onSelectionCancel.md) event for PDF API.
- Added the `EditorRestrictions` type to the simple type definitions for [Document API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/EditorRestrictions.md), [Form API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Enumeration/EditorRestrictions.md), [Spreadsheet API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Enumeration/EditorRestrictions.md), [Presentation API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Enumeration/EditorRestrictions.md), and [PDF API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/EditorRestrictions.md).
- Added the [CommentData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/CommentData.md) type to the simple type definitions for PDF API.
- Added the [comment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/comment.md) type to the simple type definitions for PDF API.
- Added the [Event_pt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/Event_pt.md) type to the simple type definitions for PDF API.

## Version 9.4

- Added the [MoveCursorToField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/MoveCursorToField.md) method for Document API.
- Added the [MoveCursorOutsideField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/MoveCursorOutsideField.md) method for Document API.
- Added the `lockScroll` and `keepSelection` parameters to the [StartAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/StartAction.md) method.
- Added the `scrollToTarget` and `cancel` parameters to the [EndAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/EndAction.md) method.

## Version 9.3

- Added the [SelectAddinField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/SelectAddinField.md) method for Document API.
- Added the [RemoveAddinField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/RemoveAddinField.md) method for Document API.
- Added the [GetCurrentAddinField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetCurrentAddinField.md) method for Document API.
- Added the [IsFormSigned](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/IsFormSigned.md) method for Document API.
- Added the [CoAuthoringChatSendMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/CoAuthoringChatSendMessage.md) method for PDF API.
- Added the [EndAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/EndAction.md) method for PDF API.
- Added the [FocusEditor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/FocusEditor.md) method for PDF API.
- Added the [GetAllComments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetAllComments.md) method for PDF API.
- Added the [GetCurrentPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetCurrentPage.md) method for PDF API.
- Added the [GetFileToDownload](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetFileToDownload.md) method for PDF API.
- Added the [GetFontList](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetFontList.md) method for PDF API.
- Added the [GetInstalledPlugins](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetInstalledPlugins.md) method for PDF API.
- Added the [GetMacros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetMacros.md) method for PDF API.
- Added the [GetPageImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetPageImage.md) method for PDF API.
- Added the [GetSelectedText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetSelectedText.md) method for PDF API.
- Added the [GetVersion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/GetVersion.md) method for PDF API.
- Added the [InstallPlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/InstallPlugin.md) method for PDF API.
- Added the [MouseMoveWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/MouseMoveWindow.md) method for PDF API.
- Added the [MouseUpWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/MouseUpWindow.md) method for PDF API.
- Added the [OnDropEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/OnDropEvent.md) method for PDF API.
- Added the [PasteHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/PasteHtml.md) method for PDF API.
- Added the [PasteText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/PasteText.md) method for PDF API.
- Added the [RemovePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/RemovePlugin.md) method for PDF API.
- Added the [ReplacePageContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/ReplacePageContent.md) method for PDF API.
- Added the [SetMacros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/SetMacros.md) method for PDF API.
- Added the [SetPluginsOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/SetPluginsOptions.md) method for PDF API.
- Added the [SetProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/SetProperties.md) method for PDF API.
- Added the [ShowButton](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/ShowButton.md) method for PDF API.
- Added the [ShowError](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/ShowError.md) method for PDF API.
- Added the [ShowInputHelper](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/ShowInputHelper.md) method for PDF API.
- Added the [StartAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/StartAction.md) method for PDF API.
- Added the [UnShowInputHelper](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/UnShowInputHelper.md) method for PDF API.
- Added the [UpdatePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Methods/UpdatePlugin.md) method for PDF API.

## Version 9.2

- Added the [AnnotateParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/AnnotateParagraph.md) method for Document API.
- Added the [RemoveAnnotationRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/RemoveAnnotationRange.md) method for Document API.
- Added the [SelectAnnotationRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/SelectAnnotationRange.md) method for Document API.
- Added the [onBlurAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Events/onBlurAnnotation.md) event for Document API.
- Added the [onClickAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Events/onClickAnnotation.md) event for Document API.
- Added the [onFocusAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Events/onFocusAnnotation.md) event for Document API.
- Added the [onParagraphText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Events/onParagraphText.md) event for Document API.
- Updated [Adding plugins through the plugin manager for all users](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/development-workflow/installing-and-testing/docs-on-premises-installation.md) instruction according Help center info.

## Version 9.1

- Added the [RemoveOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/RemoveOleObject.md) method for Spreadsheet API.
- Added the [RemoveOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/RemoveOleObject.md) method for Presentation API.

## Version 9.0

- Added the ability to access [cell address information](https://api.onlyoffice.com/ai-plugin-docs-update/docs/macros/guides/adding-custom-functions.md#accessing-cell-addresses) inside custom functions.
- Added the ability to add [asynchronous custom functions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/macros/guides/adding-custom-functions.md#asynchronous-functions) to the spreadsheets using the **Macros** plugin.
- Added the ability to [automatically convert](https://api.onlyoffice.com/ai-plugin-docs-update/docs/macros/guides/converting-vba-macros.md#automatic-conversion-using-ai-plugin) VBA code into ONLYOFFICE macros using AI plugin.
- Added the ability to [automatically generate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/macros/guides/writing-macros.md#generating-macros-using-ai-plugin) ONLYOFFICE macros using AI plugin.
- Added the ability to add custom [buttons to content controls](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/content-control-buttons.md) using a plugin.
- Added the [GetCurrentBookmark](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetCurrentBookmark.md) method for Document API.
- Added the [GoToSlide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/GoToSlide.md) method for Presentation API.
- Added the [ContentControlListElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/ContentControlListElement.md) enumeration.

## Version 8.3

- Added the [GetSelectedContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetSelectedContent.md) method.
- Added the [ShowError](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/ShowError.md) method.
- Added the `Shd` and `Border` properties to the [ContentControlProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/ContentControlProperties.md) object.
- Added the `isActivated` parameter to the [panel settings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/windows-and-panels.md#creating-a-window).

## Version 8.2

- Added the [onSubmitForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Events/onSubmitForm.md) event.
- Added the [CanRedo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/CanRedo.md) method for Document API.
- Added the [CanUndo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/CanUndo.md) method for Document API.
- Added the [Redo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/Redo.md) method for Document API.
- Added the [Undo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/Undo.md) method for Document API.

## Version 8.1

- Added the ability to [add custom functions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/macros/guides/adding-custom-functions.md) to the spreadsheets using the **Macros** plugin.
- Added the ability to add the plugin [toolbar menu items](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/toolbar.md).
- Added the ability to create [multiple left panels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/configuration/variations.md) for plugins.
- Added the information about the current position of the context menu plugin event.
- Added the `onToolbarMenuClick` event.
- Added the [ActivateWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/windows-and-panels.md#activating-a-window) method.
- Added the [AddToolbarMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/toolbar.md#addtoolbarmenuitem) method.
- Added the [GetSelectedOleObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetSelectedOleObjects.md) method.
- Added the [SetPluginsOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/SetPluginsOptions.md) method.
- Added the [GetAllComments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetAllComments.md) method for Spreadsheet API.
- Added the [GetCustomFunctions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/GetCustomFunctions.md) method for Spreadsheet API.
- Added the [SetCustomFunctions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/spreadsheet-api/Methods/SetCustomFunctions.md) method for Spreadsheet API.
- Added the [GetAllComments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/GetAllComments.md) method for Presentation API.
- Added the [OLEProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/OLEProperties.md) type to the simple type definitions.
- Added the [PluginOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/PluginOptions.md) type to the simple type definitions.
- Added the [ToolbarMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/toolbar.md#toolbarmenuitem) type to the simple type definitions.
- Added the [ToolbarMenuMainItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/toolbar.md#toolbarmenumainitem) type to the simple type definitions.
- Added the [ToolbarMenuTab](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/toolbar.md#toolbarmenutab) type to the simple type definitions.
- Added the [ToolbarMenuItemType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/toolbar.md#toolbarmenuitemtype) type to the simple type definitions.
- Added the `icons` and `data` parameters to the [ContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/asc-plugin.md#contextmenuitem) object.
- Added the [menu](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/configuration.md#variationsmenu) config parameter.

## Version 8.0

- Added the [SearchNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/SearchNext.md) method.
- Added the [EndSlideShow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/EndSlideShow.md) method.
- Added the [GoToNextSlideInSlideShow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/GoToNextSlideInSlideShow.md) method.
- Added the [GoToPreviousSlideInSlideShow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/GoToPreviousSlideInSlideShow.md) method.
- Added the [GoToSlideInSlideShow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/GoToSlideInSlideShow.md) method.
- Added the [PauseSlideShow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/PauseSlideShow.md) method.
- Added the [ResumeSlideShow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/ResumeSlideShow.md) method.
- Added the [StartSlideShow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Methods/StartSlideShow.md) method.

## Version 7.5

- Added the `align` parameter to the [ShowButton](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/ShowButton.md) method.

## Version 7.4

- Added the ability to download ready-to-use plugins from [ONLYOFFICE Plugin Marketplace](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/development-workflow/installing-and-testing/desktop-editors-installation.md#adding-plugins-through-the-plugin-manager) in ONLYOFFICE Desktop Editors.
- Added the [sendToPlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/windows-and-panels.md#interacting-with-a-window) method to the `Plugin` object.
- Added the [onContextMenuClick](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/context-menu.md#clicking-a-context-menu-item) event.
- Added the [onContextMenuShow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/context-menu.md#creating-a-context-menu-item) event.
- Added the [AddContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/context-menu.md#creating-a-context-menu-item) method.
- Added the [CloseWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/windows-and-panels.md#closing-a-window) method.
- Added the [GetCurrentSentence](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetCurrentSentence.md) method.
- Added the [GetCurrentWord](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetCurrentWord.md) method.
- Added the [GetDocumentLang](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetDocumentLang.md) method.
- Added the [MouseMoveWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/MouseMoveWindow.md) method.
- Added the [MouseUpWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/MouseUpWindow.md) method.
- Added the [ReplaceCurrentSentence](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/ReplaceCurrentSentence.md) method.
- Added the [ReplaceCurrentWord](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/ReplaceCurrentWord.md) method.
- Added the [ResizeWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/windows-and-panels.md#interacting-with-a-window) method.
- Added the [SendToWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/windows-and-panels.md#interacting-with-a-window) method.
- Added the [ShowWindow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/windows-and-panels.md#showing-a-window) method.
- Added the [UpdateContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/customization/context-menu.md#updating-a-context-menu-item) method.
- Added the `backup` parameter to the [RemovePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/RemovePlugin.md) method.
- Added the `NewLineSeparator` parameter to the [GetSelectedText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetSelectedText.md) method.
- Added the `replaceMode` parameter to the [ImageData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/ImageData.md) object.

## Version 7.3

- Added the `sign` type to the [initDataType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/configuration.md#variationsinitdatatype) config parameter.
- Added the [AddAddinField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/AddAddinField.md) method.
- Added the [GetAllAddinFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetAllAddinFields.md) method.
- Added the [GetVBAMacros](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetVBAMacros.md) method.
- Added the [OnDropEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/OnDropEvent.md) method.
- Added the [RemoveFieldWrapper](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/RemoveFieldWrapper.md) method.
- Added the [SetEditingRestrictions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/SetEditingRestrictions.md) method.
- Added the [UpdateAddinFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/UpdateAddinFields.md) method.
- Added the editor methods for Spreadsheet API.
- Added the editor methods for Presentation API.

## Version 7.2

- Added the [onAddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Events/onAddComment.md) event.
- Added the [onChangeCommentData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Events/onChangeCommentData.md) event.
- Added the [onRemoveComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Events/onRemoveComment.md) event.
- Added the [AcceptReviewChanges](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/AcceptReviewChanges.md) method.
- Added the [MoveToNextReviewChange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/MoveToNextReviewChange.md) method.
- Added the [RejectReviewChanges](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/RejectReviewChanges.md) method.
- Changed the plugin [localization](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/configuration/localization.md) scheme.
- Added the [ONLYOFFICE Plugin Marketplace](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/development-workflow/installing-and-testing/docs-on-premises-installation.md#adding-plugins-through-the-plugin-manager-for-a-single-user).
- Added the [ChangeOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/ChangeOleObject.md) method.
- Added the [GetAllForms](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetAllForms.md) method.
- Added the [GetFileToDownload](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetFileToDownload.md) method.
- Added the [GetFormsByTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetFormsByTag.md) method.
- Added the [GetFormValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/GetFormValue.md) method.
- Added the [GetImageDataFromSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetImageDataFromSelection.md) method.
- Added the [GetInstalledPlugins](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/GetInstalledPlugins.md) method.
- Added the [InstallPlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/InstallPlugin.md) method.
- Added the [PutImageDataToSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/PutImageDataToSelection.md) method.
- Added the [RemovePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/RemovePlugin.md) method.
- Added the [SetFormValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/form-api/Methods/SetFormValue.md) method.
- Added the [ShowButton](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/ShowButton.md) method.
- Added the [UpdatePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/UpdatePlugin.md) method.
- Added the [onBlurContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Events/onBlurContentControl.md) event.
- Added the [onChangeContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Events/onChangeContentControl.md) event.
- Added the [onFocusContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Events/onFocusContentControl.md) event.
