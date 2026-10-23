# setDefaultTemplate

> DefaultTemplateSettingsWrapper setDefaultTemplate(DefaultTemplateSettingsRequestDto)

`PUT /api/2.0/files/settings/defaulttemplate`

Change the default template setting

Makes an existing document the blank the portal creates for one extension, and returns the full set of templates as it now stands. The file is copied into the portal's template storage, so later edits of the original do not change the blank, and the file that served as the previous custom blank for that extension is deleted. `selectedFile` takes the identifier of a file the caller may copy - a number for a document stored in the portal, a string for one in a connected third-party storage - and its extension must be the one named in `fileExtension`; a mismatch or an identifier of another kind answers 400, a file the caller may not copy answers 403, and a file that is not there is answered as missing. An extension the built-in template set does not cover is not an error: the call succeeds and changes nothing, so compare the answer with what was asked for. Requires the portal settings permission.

## Parameters

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **DefaultTemplateSettingsRequestDto** | body | [**DefaultTemplateSettingsRequestDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/default-template-settings-request-dto.md) |  | [optional] |

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | The blank document configured for each supported extension after the change | [**DefaultTemplateSettingsWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/default-template-settings-wrapper.md) | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |
| **400** | The request body cannot be read or has no `selectedFile` or `fileExtension`, the file identifier is of an unsupported kind, or its extension is not the one requested | - | - |
| **403** | The caller has no portal-settings right, or may not copy the selected file | - | - |
| **404** | The selected file does not exist | - | - |
| **500** | The file identifier is a number that cannot be read as a 32-bit integer: fractional, in exponent notation or out of range | - | - |
| **401** | Unauthorized | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **429** | Too Many Requests. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | `Retry-After` |
| **502** | Bad Gateway. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |
| **503** | Service Unavailable. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |

## Return type

[**DefaultTemplateSettingsWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/default-template-settings-wrapper.md)

## Authorization

[Basic](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#basic), [OAuth2](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#oauth2) (scopes: read, write), [ApiKeyBearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#apikeybearer), [asc_auth_key](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#asc_auth_key), [Bearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#bearer), [OpenId](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#openid)

## HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json
