# startFileConversion

> ConversationResultArrayWrapper startFileConversion(fileId, CheckConversionRequestDto)

`PUT /api/2.0/files/file/{fileId}/checkconversion`

Start file conversion

Queues the conversion of a file into the portal's own editable format and answers with the conversion entry the caller is to poll. The whole body may be omitted, in which case the defaults apply. `outputType` names the target format and, left empty, the portal's default for that kind of document is used; `password` unlocks a protected source file; `version` converts an older version instead of the current one. `createNewIfExist` decides where the result goes: with `true` a new file is created beside the source, while with `false`, the default, the converted file that already exists is replaced. `sync=true` converts inside the request and answers with the finished result instead of a queue entry, which is only sensible for small documents. Otherwise poll `GET api/2.0/files/file/{fileId}/checkconversion` until `progress` reaches 100 and take the converted file from `file`. Only formats the portal has to convert are accepted; anything already editable, and anything it cannot convert, is answered without work being queued or rejected as an invalid request. The caller needs read access to the file. The call is mutating and not idempotent.

## Parameters

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **fileId** | path | **Integer** (int32) | The file to convert. | [required] [example: `1`] |
| **CheckConversionRequestDto** | body | [**CheckConversionRequestDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/check-conversion-request-dto.md) | The parameters of the conversion. The whole body may be omitted, in which case the defaults of the portal apply. | [optional] |

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | The conversion entry to poll, or the finished result when the conversion is synchronous | [**ConversationResultArrayWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/conversation-result-array-wrapper.md) | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |
| **401** | Unauthorized | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **429** | Too Many Requests. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | `Retry-After` |
| **500** | Internal Server Error. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **400** | Bad Request. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **502** | Bad Gateway. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |
| **503** | Service Unavailable. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |

## Return type

[**ConversationResultArrayWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/conversation-result-array-wrapper.md)

## Third-party storage

For a file or folder in a connected third-party storage the identifier is a string such as `sbox-42`, and the call differs in these parts only:

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **fileId** | path | **String** | The file to convert. | [required] [example: `sbox-42-L1JlcG9ydC5kb2N4`] |
| **ThirdPartyCheckConversionRequestDto** | body | [**ThirdPartyCheckConversionRequestDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/third-party-check-conversion-request-dto.md) | The parameters of the conversion. The whole body may be omitted, in which case the defaults of the portal apply. | [optional] |


## Authorization

[Basic](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#basic), [OAuth2](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#oauth2) (scopes: read, write), [ApiKeyBearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#apikeybearer), [asc_auth_key](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#asc_auth_key), [Bearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#bearer), [OpenId](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#openid)

## HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json
