---
sidebar_position: -2
---

# Changelog

The list of changes for ONLYOFFICE Desktop Editors API.

## Version 10.0

- Added the [--prefer-alternate-url](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/command-line-flags.md#flags) command-line flag for downloading updates from an alternate source on Windows.

## Version 9.2

- Added support for [connecting MCP servers](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/connecting-mcp-servers.md) to extend AI capabilities with custom tools and integrations.
- Added the ability to connect [ONLYOFFICE DocSpace MCP server](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/connecting-mcp-servers/docspace-mcp.md) for document management operations through AI agents.

## Version 8.1

- Added the [getViewportSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider/getting-viewport-settings.md) method to the *AscDesktopEditor* object.
- Added the [onViewportSettingsChanged](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider/getting-viewport-settings.md) event to the *AscDesktopEditor* object.

## Version 7.5

- Added the [portal:uitheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider/changing-a-theme.md) command to the *execCommand* method.
- Added the [uiTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider/login-and-logout.md#uiTheme) parameter to the *portal:login* command.

## Version 7.1

- Added the *--ascdesktop-support-debug-info-keep* flag to [run](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/debugging.md#--ascdesktop-support-debug-info-keep) the application.

## Version 7.0

- Added the [extraLogout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider.md#extraLogout) parameter to the config with DMS integration parameters.

## Version 6.4

- Added the possibility to use icons for each UI theme type in the [config](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider.md) with integration parameters.

## Version 6.3

- Added the [entryPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider.md#entryPage) parameter to the config with DMS integration parameters.
- Added the *updateEncryptionKeys* [command type](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider/encryption.md#type) to the *cloudCryptoCommand* function.

## Version 6.2

- Added [config](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider.md) with DMS integration parameters.
- Added the [execCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider/execcommand.md) method.
- Added commands for [document opening](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider/opening-documents.md).

## Version 6.1

- Added [AscDesktopEditor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider/configuring-the-interaction.md) label to userAgent.

## Version 5.6

- Added [encryption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/desktop-editors/usage-api/adding-a-dms-provider/encryption.md).
