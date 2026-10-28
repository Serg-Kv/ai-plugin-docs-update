# getCascadeProgress

> MetadataOperationWrapper getCascadeProgress(folderId)

`GET /api/2.0/files/metadata/folder/{folderId}/templates/progress`

Get cascade progress

Reports the cascade pass of a folder started by `PUT api/2.0/files/metadata/folder/{folderId}/templates` or by `PUT api/2.0/files/metadata/folder/{folderId}/templates/{templateId}`: the running one, otherwise the most recent one. The caller needs read access to the folder, the call is read-only. `templateIds` names the templates the pass propagates, so a client can show the progress next to the right template; `progress` is the share of the subtree processed, `isCompleted` tells the pass is over and `error` carries the reason of a failed one; a completed pass without an error has written every template and value it was asked for. A folder that never cascaded, or whose passes were already dropped, is answered with a completed operation without an identifier and with empty `templateIds` rather than with an error. A folder that does not exist is answered with 404.

## Parameters

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **folderId** | path | **Integer** (int32) | The folder the operation acts on. Take the identifier from a listing such as `GET api/2.0/files/@root` or `GET api/2.0/files/{folderId}`: a folder stored in the portal is numbered, while a folder in a connected third-party account is named by an opaque string. | [required] [example: `1`] |

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | Cascade operation status; a completed operation without an ID when the folder has no cascade to report | [**MetadataOperationWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/metadata-operation-wrapper.md) | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |
| **404** | No folder or room with this identifier exists | - | - |
| **401** | Unauthorized | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **429** | Too Many Requests. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | `Retry-After` |
| **500** | Internal Server Error. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **400** | Bad Request. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **502** | Bad Gateway. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |
| **503** | Service Unavailable. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |

## Return type

[**MetadataOperationWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/metadata-operation-wrapper.md)

## Authorization

[Basic](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#basic), [OAuth2](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#oauth2) (scopes: read, write), [ApiKeyBearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#apikeybearer), [asc_auth_key](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#asc_auth_key), [Bearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#bearer), [OpenId](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#openid)

## HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json
