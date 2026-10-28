# getFilesSettings

> FilesSettingsWrapper getFilesSettings()

`GET /api/2.0/files/settings`

Get file settings

Returns the whole Files configuration in one object: the caller's own preferences (trash auto-clearing, default sharing rights, hidden confirmation dialogs, archive format, section visibility), the portal-wide switches an administrator controls (third-party storages, external sharing), and the static tables a client needs to work with documents - which extensions can be viewed, edited, converted or uploaded, the URL templates for the viewer, editor and thumbnails, and the upload limits. This is the read side of the setting operations in this section: each of those answers with the one value it wrote, and only the trash auto-clearing and default-template settings have a GET of their own. Marked as allowing anonymous access because the external-link pages read the extension tables before signing in, but a caller with neither a session nor a valid link key is still rejected. The result is not filtered by role and is not paginated; fetch it once per session rather than before each file action.

## Parameters
This endpoint does not need any parameter.

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | The full set of file settings for the caller and the portal | [**FilesSettingsWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/files-settings-wrapper.md) | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |
| **401** | The caller is neither signed in nor opening an external link | - | - |
| **429** | Too Many Requests. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | `Retry-After` |
| **500** | Internal Server Error. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **502** | Bad Gateway. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |
| **503** | Service Unavailable. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |

## Return type

[**FilesSettingsWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/files-settings-wrapper.md)

## Authorization

[Basic](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#basic), [OAuth2](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#oauth2) (scopes: read, write), [ApiKeyBearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#apikeybearer), [asc_auth_key](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#asc_auth_key), [Bearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#bearer), [OpenId](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#openid)

## HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json
