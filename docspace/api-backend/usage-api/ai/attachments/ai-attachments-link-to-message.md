# aiAttachmentsLinkToMessage

> AiSuccessResponse aiAttachmentsLinkToMessage(AiAttachmentsLinkToMessageRequest)

`POST /api/2.0/ai/attachments/link-to-message`

Link to message

Binds draft attachments to the chat message that owns them, after that message has been persisted, so that deleting the message removes them too. All three of `ids`, `messageId` and `threadId` are required, and the references are verified rather than trusted: an unknown message answers 404, a message that belongs to a different thread answers 400, and attachments that no longer exist answer 404 naming each missing ID. That verification exists because the underlying binding call skips unknown IDs silently, which used to report success for a link that had not happened. Drafts stay unbound until this succeeds.

## Parameters

|Name | In | Type | Description | Notes |
|------------- | ------------- | ------------- | ------------- | -------------|
| **AiAttachmentsLinkToMessageRequest** | body | [**AiAttachmentsLinkToMessageRequest**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-attachments-link-to-message-request.md) |  | [required] |

## Responses

| Status code | Description | Type | Response headers |
|------------- | ------------- | ------------- | -------------|
| **200** | Confirms the attachments are now bound to the message. | [**AiSuccessResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-success-response.md) | - |
| **400** | The attachment or message reference is malformed. | [**AiErrorResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-error-response.md) | - |
| **401** | Missing `asc_auth_key` cookie or `Authorization` header. | [**AiErrorResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-error-response.md) | - |
| **403** | AI is disabled for this portal, the caller is a guest, or the room named by `entityId` is one the caller cannot open. Relayed from the DocSpace AI service or the Files API. | [**AiErrorResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-error-response.md) | - |
| **404** | The message or the attachment does not exist. | [**AiErrorResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-error-response.md) | - |
| **413** | The request body is larger than 100 KB, the JSON parser's limit on this route. | [**AiErrorResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-error-response.md) | - |
| **500** | Unhandled failure. The reason is logged server-side and never echoed back. | [**AiErrorResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-error-response.md) | - |

## Return type

[**AiSuccessResponse**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-success-response.md)

## Authorization

[cookieAuth](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/ai.md#cookieauth), [bearerAuth](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/ai.md#bearerauth)

## HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json
