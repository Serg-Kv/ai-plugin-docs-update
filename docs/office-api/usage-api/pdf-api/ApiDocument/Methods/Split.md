# Split

Splits current pdf file with specified pages.

## Syntax

```javascript
expression.Split(indexes);
```

`expression` - A variable that represents an [ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| indexes | Optional | number[] |  | pages indexes for split (returns result for all pages if the parameter is omitted.) |

## Returns

[PdfFile](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/PdfFile.md)
