# updateFile

> FileWrapper updateFile(fileId, UpdateFileRequest)

`PUT /api/2.0/files/file/{fileId}`

Update a file

Renames a file, restores one of its versions, or both at once, and answers with the file as it now stands. A non-empty `title` renames the file, keeping the stored extension whatever the new title says, so a rename cannot change the format; an empty or missing title leaves the name alone. A `lastVersion` above 0 restores that version the way `POST api/2.0/files/file/{fileId}/restoreversion` does, storing its content again on top of the history, while 0 or less leaves the versions untouched and answers with the file as it is - which makes this operation a read of the file when both fields are left out. The caller needs edit access, and renaming somebody else's file additionally needs room-manager rights: a member or room admin with plain editing access, read-only access, a guest and a DocSpace admin who is not a member of the room are all refused with 403, while a content creator may rename a file of their own. The call is mutating. Renaming marks the file as new for everybody else who can read it.

## Parameters

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **fileId** | path | **Integer** (int32) | The file to update. | [required] [example: `1`] |
| **UpdateFileRequest** | body | [**UpdateFileRequest**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/update-file-request.md) | The new title and the version to restore. | [required] |

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | The file after the rename, the restore, or both | [**FileWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/file-wrapper.md) | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |
| **400** | The title is longer than 165 characters, or `lastVersion` is the current version | - | - |
| **401** | An anonymous caller has no external link | - | - |
| **402** | Restoring `lastVersion` needs more space than the room or user storage quota leaves | - | - |
| **403** | The caller may not read or rename the file or change its version | - | - |
| **404** | The file id, or `lastVersion` of it, resolves to nothing, or the file is a PDF form in a form-filling room whose filling has not started and the caller may only fill forms there | - | - |
| **500** | The file is locked by somebody else, a third-party file is renamed while it is being edited, or restoring `lastVersion` fails because the file is being edited, another update of it is in progress or the new version cannot be stored | - | - |
| **429** | Too Many Requests. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | `Retry-After` |
| **502** | Bad Gateway. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |
| **503** | Service Unavailable. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |

## Return type

[**FileWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/file-wrapper.md)

## Third-party storage

For a file or folder in a connected third-party storage the identifier is a string such as `sbox-42`, and the call differs in these parts only:

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **fileId** | path | **String** | The file to update. | [required] [example: `sbox-42-L1JlcG9ydC5kb2N4`] |

Return type: [**ThirdPartyFileWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/third-party-file-wrapper.md)

## Authorization

[Basic](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#basic), [OAuth2](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#oauth2) (scopes: read, write), [ApiKeyBearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#apikeybearer), [asc_auth_key](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#asc_auth_key), [Bearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#bearer), [OpenId](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#openid)

## HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json
