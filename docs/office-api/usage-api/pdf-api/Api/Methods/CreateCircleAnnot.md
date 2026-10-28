# CreateCircleAnnot

Creates circle annotation.

## Syntax

```javascript
expression.CreateCircleAnnot(rect);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| rect | Required | [Rect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Rect.md) |  | annotation rect. |

## Returns

[ApiCircleAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCircleAnnotation.md)

## Example

Add a circle annotation to highlight an area in a PDF.

```javascript editor-pdf
// How do I draw a circle annotation in a PDF?

// Mark a region with a circular outline in a PDF.

let doc = Api.GetDocument();
let circleAnnot = Api.CreateCircleAnnot([10, 10, 160, 32]);
let page = doc.GetPage(0);
page.AddObject(circleAnnot);
```
