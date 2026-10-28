# createTextFileInMyDocuments

> FileWrapper createTextFileInMyDocuments(CreateTextOrHtmlFileRequest)

`POST /api/2.0/files/@my/text`

Create a text file in My documents

Creates a text file in the caller's own My documents section out of the text passed as the content, and answers with the stored file. The extension follows the content rather than the request: `.txt` normally, but `.html` as soon as the text contains something shaped like an HTML tag, so a snippet of markup sent here ends up as an HTML file; the extension is added to the title unless the title already ends with it. A request carrying no content is rejected as invalid. `createNewIfExist` acts the other way round than its name reads: with `true` the file that already carries this title is updated and a version appears in its history, while with `false`, which is also the default, another file is created and its title made unique, as in Notes (1).txt. A file that is locked, open in an editing session, encrypted or in Trash is not updated - a new file appears beside it instead. The call is mutating. A guest has no My documents section and is refused. To create the file in a room or another folder use `POST api/2.0/files/{folderId}/text`.

## Parameters

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **CreateTextOrHtmlFileRequest** | body | [**CreateTextOrHtmlFileRequest**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/create-text-or-html-file-request.md) |  | [optional] |

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | The created or updated text file | [**FileWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/file-wrapper.md) | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |
| **400** | The request body cannot be read or has no `title` or `content`, or the title is empty, blank or longer than 165 characters | - | - |
| **402** | The content exceeds the maximum upload size, or the file does not fit into the storage quota of the portal, the room or the user | - | - |
| **403** | The caller may not create a file in this section | - | - |
| **404** | The caller is a guest, who has no My documents | - | - |
| **401** | Unauthorized | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **429** | Too Many Requests. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | `Retry-After` |
| **500** | Internal Server Error. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **502** | Bad Gateway. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |
| **503** | Service Unavailable. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |

## Return type

[**FileWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/file-wrapper.md)

## Authorization

[Basic](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#basic), [OAuth2](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#oauth2) (scopes: read, write), [ApiKeyBearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#apikeybearer), [asc_auth_key](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#asc_auth_key), [Bearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#bearer), [OpenId](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#openid)

## HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json
