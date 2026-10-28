# CreateHighlightAnnot

Creates highlight annotation.

## Syntax

```javascript
expression.CreateHighlightAnnot(rect);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| rect | Required | [Rect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Rect.md) \| [Quad](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Quad.md)[] |  | region to apply highlight. |

## Returns

[ApiHighlightAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation.md)

## Example

Create a highlight annotation and add it to the page.

```javascript editor-pdf
// Create the highlight annot in a PDF document.

// Create the highlight annot using the PDF document API.

let doc = Api.GetDocument();
let highlightAnnot = Api.CreateHighlightAnnot([[85.04985826771654,56.70000000000001,229.27237795275593,56.70000000000001,85.04985826771654,70.9988031496063,229.27237795275593,70.9988031496063]]);
let page = doc.GetPage(0);
page.AddObject(highlightAnnot);
```
