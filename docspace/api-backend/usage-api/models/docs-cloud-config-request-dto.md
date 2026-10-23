# DocsCloudConfigRequestDto
Represents the configuration of a Docs Connect tenant.

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **tenantName** | **String** | The tenant name. | [optional] [example: `My Portal`] [minLength: 0] [maxLength: 255] [nullable] |
| **security** | [**DocsCloudSecurityConfigRequest**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/docs-cloud-security-config-request.md) | The security configuration. | [optional] |
| **server** | [**DocsCloudServerConfigRequest**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/docs-cloud-server-config-request.md) | The server configuration. | [optional] |
| **wopi** | [**DocsCloudWopiConfigRequest**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/docs-cloud-wopi-config-request.md) | The WOPI configuration. | [optional] |
| **ipFilter** | [**DocsCloudIpFilterConfigRequest**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/docs-cloud-ip-filter-config-request.md) | The IP filter configuration. | [optional] |
