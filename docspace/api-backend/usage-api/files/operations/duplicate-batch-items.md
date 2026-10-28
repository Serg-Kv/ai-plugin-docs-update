# duplicateBatchItems

> FileOperationArrayWrapper duplicateBatchItems(DuplicateRequestDto)

`PUT /api/2.0/files/fileops/duplicate`

Duplicate files and folders

Queues a background job that copies each requested file and folder next to itself, into the folder where it already is, and answers with the caller's duplicate operations, including the one just started. Poll `GET api/2.0/files/fileops` until the operation reports `finished`. The copies keep the name of the original with a numeric suffix, so nothing is overwritten and every repetition adds one more copy; duplicating a folder duplicates its content as well. No destination is taken — to place a copy somewhere else use `PUT api/2.0/files/fileops/copy`. The caller needs the rights that creating an item in that folder would need, which inside a room means room manager or content-creator rights: read or editing rights, and an item the caller has no access to at all, are refused with 403. An empty selection queues nothing and answers with the operations that are already there.

## Parameters

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **DuplicateRequestDto** | body | [**DuplicateRequestDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/duplicate-request-dto.md) |  | [optional] |

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | The duplicate operations of the caller, the one just queued included | [**FileOperationArrayWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/file-operation-array-wrapper.md) | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |
| **403** | The caller cannot create items in the folder that holds one of the listed items, or cannot copy that item | - | - |
| **404** | A listed file or folder does not exist | - | - |
| **415** | A listed file has a format the portal does not accept for upload | - | - |
| **500** | An id is a number that is not a 32-bit integer | - | - |
| **401** | Unauthorized | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **429** | Too Many Requests. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | `Retry-After` |
| **400** | Bad Request. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **502** | Bad Gateway. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |
| **503** | Service Unavailable. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |

## Return type

[**FileOperationArrayWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/file-operation-array-wrapper.md)

## Authorization

[Basic](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#basic), [OAuth2](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#oauth2) (scopes: read, write), [ApiKeyBearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#apikeybearer), [asc_auth_key](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#asc_auth_key), [Bearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#bearer), [OpenId](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#openid)

## HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json
