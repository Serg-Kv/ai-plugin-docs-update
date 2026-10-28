# DocsCloudTenantInfoDto
Represents the license and server information of a Docs Connect tenant, with usage statistics for the current period.

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **license** | [**DocsCloudLicenseInfoDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/docs-cloud-license-info-dto.md) | The license information. | [optional] |
| **server** | [**DocsCloudServerInfoDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/docs-cloud-server-info-dto.md) | The Docs Connect server information. | [optional] |
| **usersLimit** | [**DocsCloudUsersLimitDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/docs-cloud-users-limit-dto.md) | The user limits of the license. | [optional] |
| **stats** | [**DocsCloudStatsDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/docs-cloud-stats-dto.md) | The usage statistics for the current period. | [optional] |
