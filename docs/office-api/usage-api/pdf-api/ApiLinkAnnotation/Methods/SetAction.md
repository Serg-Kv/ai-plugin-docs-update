# SetAction

Sets the action executed when the link is clicked.

## Syntax

```javascript
expression.SetAction(action);
```

`expression` - A variable that represents an [ApiLinkAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLinkAnnotation.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| action | Required | [ApiBaseAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAction.md) \| null \| undefined |  | GoTo, URI, or another PDF action; null removes the action. |

## Returns

boolean
