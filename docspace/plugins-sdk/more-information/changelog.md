# Changelog

The list of changes for ONLYOFFICE Apps Plugins SDK.

## Version 3.0

For migration instructions, see [Updating a plugin to SDK 3.0.0](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/more-information/migration.md#updating-a-plugin-to-sdk-300).

- Added [IArticleNavigationPlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IArticleNavigationPlugin.md) and [IArticleNavigationItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IArticleNavigationItem.md) to embed first-class navigation items in the article sidebar.
- Added the [Section](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/enums/Section.md) enum for the `appears` property of article navigation items.
- Added the `component` property to [IInfoPanelItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IInfoPanelItem.md), [IArticleButtonItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IArticleButtonItem.md), [IMediaViewer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IMediaViewer.md), and [ISettings](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/settings/ISettings.md), and `dialogBodyComponent` to [IModalDialog](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IModalDialog.md), so a React component can be passed instead of a declarative [IBox](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IBox.md) tree. See [React components](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin.md#react-components).
- Added the *@onlyoffice/docspace-plugin-sdk/react* hooks: `usePluginAPI`, `usePluginActions`, `usePluginSettings`, `useCurrentFile`, `useCurrentUser`, and `usePluginRuntime`.
- Added [`PluginAPIClient`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/api.md#pluginapiclient) (via `usePluginAPI`) for authenticated HTTP requests to the portal, and [`PluginApiError`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/react/api.md#pluginapierror) / `isPluginApiError` for failed requests.
- Deprecated `body` in `IInfoPanelItem` and `IArticleButtonItem`, `settings` in `ISettings`, `content` in `IMediaViewer`, and `dialogBody` / `dialogFooter` in `IModalDialog`. Use `component` (`dialogBodyComponent` in `IModalDialog`) instead.
- Deprecated `onLoad` on those items and components. Load data with `useEffect` inside the React component.
- Replaced Webpack with Vite in the plugin [template](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/creating-plugin-template.md) and [build](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/building-plugin.md) process.
- Raised `minDocSpaceVersion` to `"4.0.0"`. Plugins built with SDK 3.0.0 require ONLYOFFICE Apps 4.0.0 or later.

## Version 2.1.1

- Added markdown documentation generation with TypeDoc
- Added LLM instructions for DocSpace Plugin SDK development

## Version 2.1.0

- Removed `type: "module"` from *package.json*
- Updated Webpack config in template (add `"..."` to minimizer array to save default minimizers)
- Converted const enums to regular enums
- Added `Promise<void>` return type to plugin methods `onClick` ([IFileItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IFileItem.md), [IInfoPanelItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IInfoPanelItem.md), [IMainButtonItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IMainButtonItem.md), [IProfileMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IProfileMenuItem.md))
- Made `onLoad` prop optional in [IInfoPanelItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IInfoPanelItem.md)
- Made `onClick` prop optional in [IContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IContextMenuItem.md)
- Switched from yarn to npm in `npx create-docspace-plugin`
- **DEPRECATED** `onClick` in [IContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IContextMenuItem.md) is now deprecated in favor of `onItemClick`
- **DEPRECATED** `onClick` in [IMainButtonItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IMainButtonItem.md) is now deprecated in favor of `onItemClick`
- Added `onItemClick` callback to [IContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IContextMenuItem.md) to support both string and number identifiers
- Added `onItemClick` callback to [IMainButtonItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IMainButtonItem.md) to support both string and number identifiers
- Added `PluginLocale` enum
- Added `language`, `setLanguage`, `getLanguage` properties to [IPlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IPlugin.md)
- Added `isHeaderVisible` property to [IInfoPanelItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IInfoPanelItem.md)
- Added support for CSS files
- Added `className` property to components ([IBox](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IBox.md), [IButton](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IButton.md), [ICheckbox](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/ICheckbox.md), IComboBox, [IFrame](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IFrame.md), [IImage](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IImage.md), [IInput](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IInput.md), ILabel, ISkeleton, IText, [ITextArea](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/ITextArea.md), [IToggleButton](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IToggleButton.md))
- Added `id` property to [IBox](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IBox.md)
- Added `onGroupClick`, `isGroupAction` properties to [IContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IContextMenuItem.md)
- Added `items` property to [IContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IContextMenuItem.md)
- Added selector components (Base, Files, Groups, People, Room), enums (SelectorType, RoomSearchArea, RoomsType), and actions (`showSelector`, `updateSelector`, `closeSelector`)
- Added [IFloatingOperationsButton](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IFloatingOperationsButton.md) component with progress tracking functionality and actions (`addFloatingOperationsButton`, `updateFloatingOperationsButton`, `removeFloatingOperationsButton`)
- Added [IPostMessagePlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IPostMessagePlugin.md), [IPostMessageCallbackMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/utils.md) util
- Added `navigate`, `openInfoPanel` actions to [Actions](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/enums/Actions.md)
- Added [IArticleButtonPlugin](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IArticleButtonPlugin.md), [IArticleButtonItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IArticleButtonItem.md)
- Added IconButton component
- Added ILink component
- Added [IMediaViewer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IMediaViewer.md) component, actions (`showMediaViewer`, `updateMediaViewer`, `closeMediaViewer`)
- Added `placement` property to [IContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IContextMenuItem.md)
- Added `itemId` property to [IContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IContextMenuItem.md)
- Fixed `onClick` id type in [IMainButtonItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IMainButtonItem.md), [IContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IContextMenuItem.md)

## Version 2.0

- Separated file security into a new `FilesSecurity` enum.
- Added the `fileSecurity` and `security` properties to [IFileItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IFileItem.md).
- Added the `withoutBodyPadding` and `withoutHeaderMargin` properties to [IModalDialog](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IModalDialog.md).
- Added the `updateCreateDialogModal` action to [Actions](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/enums/Actions.md).
- Added the `isAutoFocusOnError`, `errorText`, `onError`, `onChange`, `isCloseAfterCreate`, and `isCreateDisabled` properties to [ICreateDialog](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/ICreateDialog.md).
- Added the `itemSecurity` property to [IContextMenuItem](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items/IContextMenuItem.md).
