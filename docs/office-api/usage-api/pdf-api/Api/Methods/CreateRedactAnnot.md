# CreateRedactAnnot

Creates redact annotation.

## Syntax

```javascript
expression.CreateRedactAnnot(rect);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| rect | Required | [Rect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Rect.md) \| [Quad](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Quad.md)[] |  | region to apply redact. |

## Returns

[ApiRedactAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRedactAnnotation.md)

## Example

Add a redaction annotation to a PDF page.

```javascript editor-pdf
// How do I mark content for permanent removal in a PDF?

// Create a redaction area that obscures text or content in a PDF.

let doc = Api.GetDocument();
let redactAnnot = Api.CreateRedactAnnot([[85.04985826771654,56.70000000000001,229.27237795275593,56.70000000000001,85.04985826771654,70.9988031496063,229.27237795275593,70.9988031496063]]);
let page = doc.GetPage(0);
page.AddObject(redactAnnot);
```
