# aiWebSearchConfigure 400 response

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **success** | **Boolean** | True when the configuration was persisted. | [required] |
| **config** | [**AiWebSearchConfig**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-web-search-config.md) | The persisted web-search configuration. Present on success. | [optional] |
| **error** | **String** | The error message, ready to be shown to the caller. | [required] |
