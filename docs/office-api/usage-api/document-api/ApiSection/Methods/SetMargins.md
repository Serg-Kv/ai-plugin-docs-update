# SetMargins

Specifies the page margins for all the pages in this section.

Alias for [ApiSection#SetPageMargins](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/SetPageMargins.md).

## Syntax

```javascript
expression.SetMargins(left, top, right, bottom);
```

`expression` - A variable that represents an [ApiSection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| left | Required | [twips](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/twips.md) |  | The left margin width measured in twentieths of a point (1/1440 of an inch). |
| top | Required | [twips](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/twips.md) |  | The top margin height measured in twentieths of a point (1/1440 of an inch). |
| right | Required | [twips](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/twips.md) |  | The right margin width measured in twentieths of a point (1/1440 of an inch). |
| bottom | Required | [twips](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/twips.md) |  | The bottom margin height measured in twentieths of a point (1/1440 of an inch). |

## Returns

boolean
