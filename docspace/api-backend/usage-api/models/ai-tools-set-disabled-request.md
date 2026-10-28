# AiToolsSetDisabledRequest

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **serverType** | **String** |  | [required] |
| **toolNames** | **List** | Tool names to disable. | [required] |
| **entityId** | **String** |  | [optional] |
| **scope** | [**AiChatToolPrefsScope**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-chat-tool-prefs-scope.md) | The list the write lands in; omitted means the caller's own. | [optional] [enum: `user`, `tenant`] |
