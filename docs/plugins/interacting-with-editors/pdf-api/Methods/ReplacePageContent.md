# ReplacePageContent

Replaces the page content with the specified parameters.

## Syntax

```javascript
expression.ReplacePageContent(nPage, oParams);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| nPage | Required | number |  | The page index. |
| oParams | Required | object |  | The replacement parameters. |
| oParams.type | Required | "xml" \| "html" |  | The type of content to be replaced (XML / HTML). |
| oParams.options | Required | [ReplaceXmlOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/ReplaceXmlOptions.md) \| [ReplaceHtmlOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/pdf-api/Enumeration/ReplaceHtmlOptions.md) |  | The content replacement options. |

## Returns

boolean
