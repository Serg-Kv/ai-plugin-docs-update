# AiFolderMutationResult
Outcome of `createFolder` / `renameFolder` — either the persisted folder or a field-scoped error.

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **success** | **Boolean** | True when the folder was persisted. | [required] [example: `true`] |
| **folder** | [**AiPromptFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-prompt-folder.md) | The persisted folder. Present on success. | [optional] |
| **error** | [**AiErrorData**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-error-data.md) | Why the folder was rejected. Present on failure. | [optional] |
