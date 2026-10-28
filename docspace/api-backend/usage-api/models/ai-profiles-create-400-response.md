# aiProfilesCreate 400 response

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **success** | **Boolean** | True when the profile was persisted. | [required] |
| **profile** | [**AiProfile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-profile.md) | The persisted profile. Present on success. | [optional] |
| **error** | **String** | The error message, ready to be shown to the caller. | [required] |
