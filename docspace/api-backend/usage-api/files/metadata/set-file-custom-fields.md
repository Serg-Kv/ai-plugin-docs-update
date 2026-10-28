# setFileCustomFields

> CustomFieldValueArrayWrapper setFileCustomFields(fileId, SetCustomFields)

`PUT /api/2.0/files/metadata/file/{fileId}/customfields`

Set file custom fields

Sets the custom text fields of a file: free-form name and value pairs that need no template. The caller needs the right to edit the file. A field is addressed by its name regardless of case: a listed name gets the value, a null or empty value removes the field from the file, the names not listed are left alone, so a partial request is safe. A name the portal has not seen yet creates the field for the whole portal, and a name no entry holds a value for any more is dropped, so the set of names follows the values. A name is at most 255 characters, a value at most 8000, a name may be listed once and a file holds at most 50 custom fields. The write finishes in the request; the values take part in the free text search and in the `metadataFilters` of the listings. The answer is the custom fields of the file after the write. An empty list, a blank, repeated or over-long name, an over-long value or more than 50 fields is answered with 400; a file the caller cannot edit with 403; a file that does not exist with 404.

## Parameters

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **fileId** | path | **Integer** (int32) | The file ID. | [required] [example: `1`] |
| **SetCustomFields** | body | [**SetCustomFields**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/set-custom-fields.md) | The custom fields to set. | [required] |

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | The custom fields of the file with their values | [**CustomFieldValueArrayWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/custom-field-value-array-wrapper.md) | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |
| **400** | Invalid custom fields or too many of them | - | - |
| **403** | You don't have enough permission to perform the operation | - | - |
| **404** | No file with this identifier exists | - | - |
| **401** | Unauthorized | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **429** | Too Many Requests. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | `Retry-After` |
| **500** | Internal Server Error. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **502** | Bad Gateway. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |
| **503** | Service Unavailable. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |

## Return type

[**CustomFieldValueArrayWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/custom-field-value-array-wrapper.md)

## Authorization

[Basic](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#basic), [OAuth2](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#oauth2) (scopes: read, write), [ApiKeyBearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#apikeybearer), [asc_auth_key](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#asc_auth_key), [Bearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#bearer), [OpenId](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#openid)

## HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json
