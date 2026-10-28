# addFavorites

> BooleanWrapper addFavorites(BaseBatchRequestDto)

`POST /api/2.0/files/favorites`

Add favorite files and folders

Marks the listed files and folders as favorites for the calling account. The favorite list is personal: nothing changes for other members, and the entries stay where they are stored. Read access to each item is enough, so a room member with view-only rights and a guest may call it. Items the caller cannot read, ids that do not exist and encrypted files of a private room are skipped without a word, and the answer is `true` even when nothing was marked, so read the outcome back from `GET api/2.0/files/@favorites` instead of trusting it. Numeric ids address entries stored in the portal itself, string ids entries on a connected third-party account, and both kinds may be sent in one request. The call is mutating but safe to repeat: an item already marked stays listed once. An entry moved to the Trash keeps its mark and is left out of the listing until it is restored. `returnSingleOperation` arrives with the shared body and does nothing here. Use `DELETE api/2.0/files/favorites` to undo, or `GET api/2.0/files/favorites/{fileId}` for a single file.

## Parameters

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **BaseBatchRequestDto** | body | [**BaseBatchRequestDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/base-batch-request-dto.md) |  | [optional] |

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | Always true: the request was understood, which does not mean that anything was marked | [**BooleanWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/boolean-wrapper.md) | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |
| **400** | The request body cannot be read, or a third-party identifier refers to a storage account that is not connected | - | - |
| **403** | Marking favorites is refused for the caller | - | - |
| **404** | A third-party identifier names a storage type the portal does not know | - | - |
| **500** | An id is a number that is not a 32-bit integer, or a third-party identifier carries a storage account number beyond the 32-bit range | - | - |
| **401** | Unauthorized | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | - |
| **429** | Too Many Requests. | [**ErrorApiResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/error-api-response.md) | `Retry-After` |
| **502** | Bad Gateway. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |
| **503** | Service Unavailable. Returned by the reverse proxy, response body may be HTML and not JSON. | - | - |

## Return type

[**BooleanWrapper**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/boolean-wrapper.md)

## Authorization

[Basic](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#basic), [OAuth2](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#oauth2) (scopes: read, write), [ApiKeyBearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#apikeybearer), [asc_auth_key](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#asc_auth_key), [Bearer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#bearer), [OpenId](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files.md#openid)

## HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json
