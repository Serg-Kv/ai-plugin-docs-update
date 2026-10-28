# finalizeSession

> UploadSessionResponseWrapper finalizeSession(folderId, sessionId)

`PUT /api/2.0/files/{folderId}/session/{sessionId}/finalize`

Finalize an upload session

Assembles the parts received so far into the file the session was opened for and closes the session. What comes out depends on how the session started: one opened against an existing file through `POST api/2.0/files/file/{fileId}/edit_session` replaces that content in place and keeps the version number, while one opened against a folder either creates the file or, when a file of the same name was taken over, stores the content as its next version. A form loses its filling state on the way in. The answer arrives with 201 and carries the identifiers of the file together with the file itself. The call ends the session: the record and the buffered parts are removed, so it cannot be repeated and there is nothing left to abort afterwards. Running it before all the declared bytes have arrived assembles whatever is there, so read the progress from the chunk calls first. An unknown, already closed or expired session id fails instead of answering as missing.

## Parameters

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **folderId** | path | **Integer** (int32) | The folder the session was opened against. It is part of the route only and is not matched against the session, which is found by its own id. | [required] [example: `1`] |
| **sessionId** | path | **String** | The session to assemble, as returned in `id` when it was created: a 32-character hexadecimal string that identifies the session on its own. | [required] [example: `9f1c7a2b4d3e4f5a8b6c0d1e2f3a4b5c`] |

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | The assembled file and the identifiers of the closed session | [**UploadSessionResponseWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/upload-session-response-wrapper.md) | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |
| **400** | The parts received so far do not add up to the size the session was opened for | - | - |
| **402** | Storing the file would exceed a storage quota or size limit | - | - |
| **404** | No open session with the specified ID: it never existed, was finalized or aborted, or has expired | - | - |
| **500** | A file that is not a PDF is stored in a form-filling room | - | - |
| **401** | Unauthorized | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **429** | Too Many Requests. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | `Retry-After` |
| **502** | Bad Gateway. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |
| **503** | Service Unavailable. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |

## Return type

[**UploadSessionResponseWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/upload-session-response-wrapper.md)

## Third-party storage

For a file or folder in a connected third-party storage the identifier is a string such as `sbox-42`, and the call differs in these parts only:

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **folderId** | path | **String** | The folder the session was opened against. It is part of the route only and is not matched against the session, which is found by its own id. | [required] [example: `sbox-42`] |

Return type: [**ThirdPartyUploadSessionResponseWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/third-party-upload-session-response-wrapper.md)

## Authorization

[Basic](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#basic), [OAuth2](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#oauth2) (scopes: read, write), [ApiKeyBearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#apikeybearer), [asc_auth_key](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#asc_auth_key), [Bearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#bearer), [OpenId](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#openid)

## HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json
