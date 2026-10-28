# copyBatchItems

> FileOperationArrayWrapper copyBatchItems(BatchRequestDto)

`PUT /api/2.0/files/fileops/copy`

Copy files and folders

Queues a background job that copies the requested files and folders into `destFolderId`, leaving the originals where they are, and answers with the caller's move and copy operations, including the one just started. Poll `GET api/2.0/files/fileops` until the operation reports `finished`; its `files` and `folders` then name what was produced. Before starting, `GET api/2.0/files/fileops/move` reports which items already have a same-named entry at the destination and `conflictResolveType` decides what happens to them, while `GET api/2.0/files/fileops/checkdestfolder` reports whether the destination accepts the files at all. The caller needs create access to the destination — room manager or content-creator rights inside a room — and read access to every source item; anything less is refused with 403. With `content=true` each listed folder is replaced by its own files and subfolders, so the folder itself is not recreated at the destination. An empty selection queues nothing and answers with the operations that are already there. To remove the originals instead use `PUT api/2.0/files/fileops/move`.

## Parameters

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **BatchRequestDto** | body | [**BatchRequestDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/batch-request-dto.md) |  | [optional] |

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | The move and copy operations of the caller, the one just queued included | [**FileOperationArrayWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/file-operation-array-wrapper.md) | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |
| **403** | The caller cannot create items in the destination folder or cannot read one of the listed items, the destination is a listed folder or lies inside one, the room or user quota would be exceeded, a file that is not a PDF form goes to a form-filling room, or a file to overwrite is locked or cannot be edited by the caller | - | - |
| **404** | The destination folder, a listed file or a listed folder other than the first one does not exist | - | - |
| **415** | A listed file has a format the portal does not accept for upload, or one a knowledge folder cannot index | - | - |
| **500** | The first listed folder does not exist, or an id is a number that is not a 32-bit integer | - | - |
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
